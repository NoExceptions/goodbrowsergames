# Back End API
Seguem aqui os detalhes da arquitetura da API de back-end do GoodBrowserGames

## Diagrama de Classes
O diagrama de classes abaixo descreve todos os tipos de elementos que existem no sistema atual:

```mermaid
classDiagram
  direction RL
  class User {
    -id : string
    -nome : string
    -email: string
    -password :string
  }
  class Role{
    -id : string
    -name : string
  }
  class SessionToken{
    -id : string
    -created_at: datetime
    -updated_at: datetime
  }

    class BrowserGame{
    -id : string
    -created_at: datetime
    -updated_at: datetime
    -name: string
    -gameURL: string
    -videoURL: string
    -description: string
  }

class Evaluation{
    -id: string
    -texto: string
    -nota: double
}

class Category{
    -id : string
    -name: string
}
  User "1" --o "*" Role : possui
  User "1" --o "*" BrowserGame : possui
  SessionToken "1" --o "1" User : pertence
  BrowserGame "1" --* "*" Evaluation : possui
  BrowserGame "1" --o "1" Category : possui
  Evaluation "1*" --* "1" User : criada por
  ```
