## Uso de casos e funcionalidades
### 1. Uso de caso: Primeiro contato com o sistema e nívies de acesso
O diagrama abaixo mostra qual comportamento cada tipo de usuário deverá ter com o sistema em seu primeiro contato.
![Uso de caso logon](/docs/imgs/overview_acesso.png)
### Serviço de Atualização de Recomendações
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
