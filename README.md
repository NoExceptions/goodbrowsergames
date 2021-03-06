# goodbrowsergames
Uma página web para avaliação de jogos em browser. Hoje em dia temos muitos jogos que rodam direto do nosso navegador, além de ótimos passatempos temos a facilidade de ter um momento de lazer sem precisar de se envolver no processo de instalação de um jogo. A ideia do **goodbrowsergames** é criar uma plataforma para diversos usuários poderem avaliar quais jogos sugeridos no site realmente valeram a pena!

## URLs importantes

#### Código-fonte

O código fonte se encontrará neste próprio repositório.


#### Projeto em Execução (Versõ Nightly)

Quando em desenvolvimento nosso projeto funcionará através do Heroku, clique [aqui para visualizar a versão mais recente](https://goodbrowsergames-web.herokuapp.com/) em funcionamento. Ou use o link:  
https://goodbrowsergames-web.herokuapp.com/

Nosso sistema possuirá dois servidores um para servir de front-end e outro de API com persistencia em banco de dados, clique [aqui para visualizar a versão mais recente](https://goodbrowsergames-api.herokuapp.com/). Ou use o link:  
https://goodbrowsergames-api.herokuapp.com/
## Detalhamento das Necessidades do Projeto
O detalhamento de engenharia de software deste projeto pode ser encontrado na pasta docs deste repositório. Para facilitar o entendimento e navegabilidade do projeto os links abaixo podem ser utilizados.  

### [Requisitos](docs/reqs.md)
Todos os requisitos funcionais e não funcionais elencados para este sistema estarão descritos neste local.
### [Casos de Uso e Funcionalidades](docs/usecases.md)
Use este link para navegar diretamente para todos o detalhamento de cada etapa do sistema.

## Arquitetura do Projeto
O projeto será desenvovlido em dois sistemas que se comunicam, um será o uma API Rest de Backend que disponibilizará métodos rest para o outro sistema que chamaremos aqui de front-end consumir.

### Diagrama de Implementação
![image](docs/imgs/diag_implant.png)

### [Back-end](docs/backend.md)
### [Front-end](docs/frontend.md)

<br />

# =-=-=-=-=-=-=-=-=-=-=-=-=-=-=

<br />

# Para o front-end do projeto:

Se não tiver o Angular CLI instalado, instale-o com o comando:
```
npm install -g @angular/cli
```

Compile a aplicação com:
```
npm run build
```

E inicialize usando:
```
npm start
```

# Para o back-end

Inicie a API com
```
npm start
```
