## Uso de casos e funcionalidades
### 1. Primeiro contato com o sistema 1 nívies de acesso
O diagrama abaixo mostra qual comportamento cada tipo de usuário deverá ter com o sistema em seu primeiro contato.
![Uso de caso logon](/docs/imgs/overview_acesso.png)

### 2. Logon no Sistema

Uso de Caso   | Acesso a dados protegidos
--------------|------------
Pré-Condições  | Usuário já registrado
Pós-Condições  | Acesso ao conteúdo protegido de acordo com permissão do usuário logado

#### Fluxo Principal 
1. Usuário acessa efetuar login / ou tenta acessar um conteúdo protegido sem estar logado
2. Sistema pede usuario, senha e um captcha (para evitar mútliplas tentativas)
3. Usuário entra com os dados solicitados
4. Sistema verifica o acesso
5. O sistema valida a sessão e passa a permitir os acessos destinados aquele usuário

#### Fluxo alternativo
1. Se a senha estiver inválida o sistema volta ao passo 2 e destaca a pergunta se o usuário esqueceu sua senha

### 3. Cadastro de novos membros

Uso de Caso   | Cadastro de novos usuários
--------------|------------
Pré-Condições  | Nenhuma
Pós-Condições  | Cadastro de usuário efetuado com sucesso, nível de acesso standard: Membro

### 4. Cadastro/Edição de Browser Games

Uso de Caso   | Cadastro de Browser Games
--------------|------------
Pré-Condições  | Usuário logado com nível de administrador
Pós-Condições  | Cadastro ou alteração de browser game efetuado com sucesso

### 5. Cadastro/Edição de Categorias

Uso de Caso   | Cadastro de Categorias
--------------|------------
Pré-Condições  | Usuário logado com nível de administrador
Pós-Condições  | Cadastro ou alteração de categoria efetuado com sucesso

### 6. Pesquisa de jogos

Uso de Caso   | Pesquisa de Jogos
--------------|------------
Pré-Condições  | Usuário logado
Pós-Condições  | Lista de jogos conforme tipo de busca

#### Fluxo Principal 
1. Usuário precisará logado e navegar até uma interface de busca
2. a busca poderá ser feita pelo nome do jogo (possível inserir o nome parcialmente) e/ou por escolha de uma categoria
3. Usuário entra com os dados solicitados
4. Sistema realiza a busca
5. O sistema retorna a lista de jogos de acordo com a busca

#### Fluxo alternativo
1. Uma tela didática será retornada caso não seja encontrado nenhum jogo durante a busca

### 14. Serviço de Atualização de Recomendações
O diagrama abaixo registra quando o serviço de recomendações é disparado para atualizar as recomendações de um determinado membro. Essas recomendações são atualizadas a cada logon do usuário. De forma assíncrona, ou seja, assim que determinado membro é logado um sub-serviço será disparado para atualizar as recomendações.  
**As recomendações sempre serão solicitadas estaticamente daquilo que está no banco de dados no momento da solicitação. O sistema que  eventualemnte atualizará os dados no banco.**
```mermaid
sequenceDiagram
    participant Membro
    participant Sistema
    participant Serviço de Recomendações
    Membro->>Sistema: Logon
    loop
        Sistema->>Sistema: Verifica acesso
    end
    Sistema->>Membro: Sessão liberada ok!
    Sistema ->> Serviço de Recomendações: Solicita update recomendações
    loop
        Serviço de Recomendações->>Serviço de Recomendações: atualiza recomendações para usuário
    end
    Serviço de Recomendações-->>Sistema: Retorna recomendações atualizadas e persiste no banco
```
