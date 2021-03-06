# Casos de Testes

## Caso de Uso: Serviço de Atualização de Recomendações
### Cenário 1: atualização de recomendações
O sistema de atualização de recomendação roda de forma assíncrona, desta forma o teste de Atualização de Recomendações deverá ser chamado manualmente ou toda vez que o servidor http for reiniciar.

- O teste será sempre feito com o ultimo usuário que logou no sistema, caso não seja escolhido um manualmente por quem está pedindo o teste
- Sistema irá verificar as ultimas avaliações do usuário para decidir qual a categoria de jogos que o usuário prefere
- Sistema irá sugerir os jogos mais recentes e/ou menos avaliados respectivamente, serão sugeridos jogos de todas as categorias, porém, categorias preferidas terão maior peso.

##### Resultado esperado

- Um array de jogos sugeridos para determinado usuário que deverá ser retornado via console.

##### Resultados do Teste

	- Um erro inexperado (falha de comunicação ou erro de código)
	- Um array de jogos para o usuário escolhido durante teste
	- A validação poderá ser complexa, uma vez que o sistema pode não estar atualizando, então, o tester NÃO deverá considerar a resposta do array como correta diretamente, deve ser avaliado se o sistema é capaz de mudar essa seleção conforme o cenário mude.

**Valores possíveis:** SUCESSO, FALHA
<br>
<br>

## Caso de Uso: Cadastro de Usuário
### Cenário 1: Cadastro bem-sucedido:

Cadastro bem-sucedido:

- Preenchimento do campo email com um email válido (exemplo: diego@gmail.com) que ainda não foi cadastrado.
- Preenchimento do campo nome com um nome válido e não nulo (exemplo: Diego)
- Preenchimento do campo senha com uma string de mais de 6 caracteres (exemplo: diego123)
- Confirme a senha novamente no campo de confirmação.
- Clicar no botão de cadastro


##### Resultado esperado: 
  - O sistema deverá apresentar a mensagem “Cadastro realizado com sucesso”
	- O sistema deverá redirecionar para home de jogos após o cadastro.


##### Resultado do teste:
	- Realizei um teste com um email válido e tudo funcionou normalmente.
	- Realizei um teste com um email já cadastrado e o sistema retornou a mensagem que o usuário já está cadastrado, conforme o esperado.


### Cenário 2: Usuário já cadastrado:

Usuário já cadastrado::

- Preenchimento do campo email com um email válido (exemplo: diego@gmail.com) que ainda já está cadastrado no banco de dados.
- Preenchimento do campo nome com um nome válido e não nulo (exemplo: Diego)
- Preenchimento do campo senha com uma string de mais de 6 caracteres (exemplo: diego123)
- Confirme a senha novamente no campo de confirmação.
- Clicar no botão de cadastro


##### Resultado esperado: 
  - O sistema deverá apresentar a mensagem “O usuário já está cadastrado”
	- O sistema deverá redirecionar para página de login.


##### Resultado do teste:
	- Realizei um teste com um email válido e tudo funcionou normalmente.
	- Realizei um teste com um email já cadastrado e o sistema retornou a mensagem que o usuário já está cadastrado, conforme o esperado e me redirecionou para página de login.
  
  
### Cenário 3: Email inválido

- Preenchimento do campo email com um email inválido (exemplo: diego123)
- Preenchimento do campo nome com um nome válido e não nulo (exemplo: Diego)
- Preenchimento do campo senha com uma string de mais de 6 caracteres (exemplo: diego123)
- Confirme a senha novamente no campo de confirmação.
- Clicar no botão de cadastro


##### Resultado esperado: 
  - O sistema deverá apresentar a mensagem “Email inválido”
	- O sistema deverá permanecer na mesma tela de cadastro, mostrando o erro enquanto o email continuar inválido.


##### Resultado do teste:
	- Realizei um teste com um email válido e tudo funcionou normalmente.
	- Realizei um teste com um email já cadastrado e o sistema retornou a mensagem que o usuário já está cadastrado, conforme o esperado.
  
  
### Cenário 4: Senhas não conferem:


- Preenchimento do campo email com um email inválido (exemplo: diego123)
- Preenchimento do campo nome com um nome válido e não nulo (exemplo: Diego)
- Preenchimento do campo senha com uma string de mais de 6 caracteres (exemplo: diego123)
- Digite uma senha diferente
- Clicar no botão de cadastro


##### Resultado esperado: 
  - O sistema deverá apresentar a mensagem “Confirme a senha corretamente”
	- O sistema deverá permanecer na mesma tela de cadastro, mostrando o erro enquanto a senha continuar diferente.


##### Resultado do teste:
	- Realizei um teste digitando a senha 123456 no primeiro campo e 654321 no segundo e o sistema apresentou a mensagem correta, apontando o erro e me impendindo de continuar.
  


## Caso de Teste: Fluxo de Avaliação de Jogos
### Cenário 1: Fluxo de avaliação

**Caso de uso em que se baseia**: Avaliar jogos

Usuário “Gabriel” deve avaliar um jogo com 5 estrelas. Essa avaliação deve contar um número a mais na contagem de avaliações do jogo, e deve ficar salva no perfil do usuário.

##### Passos do Teste
1. Enviar uma avaliação ao ID de um jogo
2. Garantir que a contagem de avaliações e a média do jogo foram alteradas
3. Garantir que essa avaliação consta nas informações do usuário

##### Resultados do Teste
	- As estrelas de avaliação devem ficar coloridas na tela de avaliação.

**Valores possíveis:** SUCESSO, FALHA

## Caso de Teste: Gestão de Membros
### Cenário 1: Acesso à interface

**Caso de uso em que se baseia**: Acessar as interfaces para gerir os membros/usuários do sistema

O acesso deverá ser feito primeiramente com um usuário administrador e depois com um membro, com o intuito de garantir que a segurança do sistema não foi comprometido.

##### Passos do Teste
1. Logar como um usuário administrador
2. Tentar acessar via url a interface de gestão de membros.
3. Garantir que o acesso seja concedido
4. Logar como um usuário membro (que não seja administrador)
5. Tentar acessar via url a interface de gestão de membros.
6. Garantir que o acesso seja proibido

##### Resultados do Teste
	- Acesso a interface solicitada com o usuário administrador
	- Acesso negado (Not Found por exemplo) com usuário membro

**Valores possíveis:** SUCESSO, FALHA

### Cenário 2: Listagem de Usuários

**Caso de uso em que se baseia**: Ver todos os membros do sistema através da interface de gestão

O sistema deverá ser capaz de listar todos os usuários do sistema nessa interface.

##### Passos do Teste
1. Logar como um usuário administrador
2. Tentar acessar via url a interface de gestão de membros.
3. Garantir que o acesso seja concedido
4. Checar se a listagem dos usuários estão consistentes com a base (conferir se a quantidade de usuários listados bate com o banco de dados)

##### Resultados do Teste
	- A contagem de usuários coincide com a base de dados

**Valores possíveis:** SUCESSO, FALHA

### Cenário 3: Alteração e exclusão de usuário

**Caso de uso em que se baseia**: Alterar os dados de um membro

O sistema deverá permitir que o administrador altere dados de um membro:
- Nome
- Email
- Password (poderá reenviar uma reset de seha por email)
- Nível de acesso (tornar mabrom um administrador e vice-versa)

##### Passos do Teste
1. Logar como um usuário administrador
2. Tentar acessar via url a interface de gestão de membros.
3. Garantir que o acesso seja concedido
4. Escolher um usuário na listagem para ser alterado e confirmar se as alterações surtiram efeito

##### Resultados do Teste
	- Um usuário atualizado com as alterações feitas durante o teste

**Valores possíveis:** SUCESSO, FALHA



## Caso de Uso: Cadastro de Jogo

### Cenário 1: Cadastro bem-sucedido

**Caso de uso em que se baseia**: Cadastrar jogos

Usuário "A" deve cadastrar um jogo com nome, descrição, desenvolvedor e capa. Esse cadastro deve ser registrado no banco de dados e uma página de detalhes deve se fazer disponível.

##### Passos do Teste
1. Preenchimento do nome do jogo com um nome válido (não-nulo)
2. Preenchimento da descrição do jogo
3. Preenchimento do campo de desenvolvedor (empresa ou indivíduo)
4. Inserção da imagem que serve como capa do jogo
5. Clique no botão de cadastro
6. Garantir que o usuário é redirecionado a uma página de detalhes do jogo com as informações inseridas.

##### Resultados do Teste:
  - O sistema deverá apresentar a mensagem "Cadastro realizado com sucesso"
  - O sistema deverá redirecionar para a página de detalhes do jogo cadastrado

**Valores possíveis:** SUCESSO, FALHA

### Cenário 2: Erro de cadastro

##### Passos do Teste
1. Preencho todos os campos, menos o campo de nome (único campo necessário)
2. Clique no botão de cadastro
3. Recebo feedbacks visuais de erro

##### Resultado esperado:
  - Um highlight de erro deve aparecer no campo "nome"
  - Um "toast" deve aparecer na tela com uma mensagem de erro



## Caso de Uso: Interface de Jogo

### Cenário 1: Interface de Jogo

**Caso de uso em que se baseia**: Interface de Jogo

Usuário deve estar logado e com o jogo escolhido

##### Passos do Teste
1. Usuário deve acessar sistema com login e senha
2. Ao acessar, usuário irá acessar a interface de busca
3. Inserir na barra de busca o nome do jogo completo ou parcial do jogo e/ou a
categoria
4. Sistema irá fazer a busca com os dados informados
5. Usuário escolherá o jogo e clicará em confirmar
6. Ao escolher o jogo, será apresentado ao usuário tela contendo as principais
informações sobre o jogo
7. Usuário poderá realizar e alterar sua própria avaliação do jogo
8. Após usuário realizar avaliação, esta avaliação será apresentada no topo da página.
9. Se administrador o usuário poderá remover qualquer comentário de qualquer
membro

##### Resultados do Teste:
• O sistema deverá apresentar todas as informações importantes referentes ao jogo
que foi buscado pelo usuário no sistema.

**Valores possíveis**: SUCESSO, FALHA

### Cenário 2: Usuário não consegue remover comentário de outro
membro

##### Passos do Teste
1. Usuário entra com login e senha que não seja administrador
2. Ao acessar, usuário irá acessar a interface de busca
3. Inserir na barra de busca o nome do jogo completo ou parcial do jogo e/ou a
categoria
4. Sistema irá fazer a busca com os dados informados
5. Usuário escolherá o jogo e clicará em confirmar
6. Ao escolher o jogo, será apresentado ao usuário tela contendo as principais
informações sobre o jogo
7. Usuário verifica a avaliação que quer remover, mas sistema não habilita essa opção
Resultado esperado:
• Não acontecerá nenhuma alteração na tela, uma vez que, não será habilitado a
opção de “remover”, que só é apresentada quando o usuário acessa o sistema com
login e senha de administrador.



## Caso de Uso: Pesquisa de Jogos

### Cenário 1: Pesquisa de Jogos

**Caso de uso em que se baseia**: Pesquisa de Jogos

Usuário deve estar logado para realizar a pesquisa de jogos

##### Passos do Teste
1. Usuário deve acessar sistema com login e senha
2. Ao acessar, usuário irá acessar a interface de busca
3. Inserir na barra de busca o nome do jogo completo ou parcial do jogo e/ou a
categoria
4. Sistema irá fazer a busca com os dados informados
5. Garantir que o sistema retornará a lista de jogos de acordo com a busca realizada
pelo usuário
Resultados do Teste:
• O sistema deverá apresentar a lista de jogos de acordo com a busca realizada pelo
usuário
• Os jogos serão apresentados em uma lista ordenados pelo nome alfabeticamente

**Valores possíveis**: SUCESSO, FALHA

### Cenário 2: Erro na pesquisa do jogo

##### Passos do Teste
1. Usuário insere algum caractere incorreto ou nome que não tem na lista de jogos
cadastrados no sistema
2. Clique no botão de “Buscar”
3. Aparece tela mostrando como realizar as buscas
Resultado esperado:
• Uma tela didática será retornada caso não seja encontrado nenhum jogo durante a
busca



## Caso de Uso: Cadastro/Edição de Categorias

### Cenário 1: Cadastro/Edição bem-sucedido

**Caso de uso em que se baseia**: Cadastro / Edição de Categorias

Usuário deve estar logado com nível de administrador para ter acesso ao sistema de
cadastro e edição.

##### Passos do Teste
1. Usuário deve acessar sistema com login e senha de administrador
2. Ao acessar, usuário irá para página de Categorias onde poderá cadastrar ou editar
as categorias dos Jogos.
3. Realizar o cadastro/edição da categoria
4. Confirmar o cadastro/edição clicando no botão “Alterar”
5. Garantir que o usuário conseguiu realizar as alterações

##### Resultados do Teste:
• O sistema deverá apresentar a mensagem “Cadastro/Edição realizado com sucesso”
• O sistema deverá redirecionar para a página de de categorias, com a alteração
realizada.

**Valores possíveis**: SUCESSO, FALHA

### Cenário 2: Erro de cadastro/edição de Categorias

##### Passos do Teste
1. Não seleciona a categoria que deseja cadastrar/editar;
2. Clique no botão de “Alterar”
3. Recebo feedbacks visuais de erro

##### Resultado esperado:
• Um pop-up deve aparecer informando “Categoria não selecionada”
