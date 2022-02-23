## Requisitos
### Requisitos Funcionais
Foram listados pelos stakeholders as seguintes funcionalidades:  
1. O administrador do **GoodBrowserGames** será responsável por cadastrar os *browser games* a serem avaliadaos.
2. Os games serão classificados quanto a sua categoria, caberá ao administrador adicionar ou editar categorias. Inicialmente as seguintes categorias serão criadas:  
    - Action
    - Adventure
    - Arcade
    - Puzzle
    - RPG
    - Shooter
    - Sport
    - Strategy
    - RPG (Role Playing Game)


 3. Ao cadastrar um game browser as seguintes informações deverão ser repassadas pelo administrador:  
    - Nome do Jogo
    - Categoria (Escolhida de uma lista de categorias)
    - Descrição (Com até 255 charcateres)
    - URL do Jogo
    - URL contendo, se possível, video de demo do jogo


4. Qualquer pessoa pode ser membro do **GoodBrowserGames** para isso ela deverá fornecer os seguintes dados no momento de cadastro:
    - Nome completo
    - Usuário - que deverá ser único no sistema
    - Senha
    - Data de Nascimento
    - Estado
    - País

5. O membro poderá buscar por um game de duas formas:
    - Buscando pelo nome do jogo ou por parte do nome
    - Buscando por categoria, neste caso após escolher uma categoria será fornceido uma lista em ordem alfabética com os games da categoria escolhida

6. Quando um membro escolher determinado jogo através da busca, ele poderá avaliá-lo, usando:
    - Uma categoria de 1 a 5 estrelas
    - Uma descrição da avaliação em até 255 caracteres  
    Caso já tenha sido feita uma avaliação no passado o usuário poderá modificar sua avaliação do jogo.

7. Ao mesmo tempo, quando um jogo estiver selecionado o membro poderá ver todas as avaliações dos demais mebros para aquele game.

8. O membro poderá classificar uma avalição como útil.

9. Um membro poderá solicitar as avaliações mais úteis do **GoodBrowserGames** ordenada pelo numero de votações como útil.

10. Devera ter no sistema um local para um membro ver *recomendações* de jogos que ele ainda não avaliou. Para dar essa recomendação o **GoodBrowserGames** deverá utilizar um algoritimo, esse algorítimo deve estar detalhado nos requisitos do software.

11. O administrador poderá obter os seguintes relatórios, por período de tempo (data inicial e final):
    1. 5 Jogos com o maior número de avaliações
    2. 5 Membros que mais avaliam
    3. 5 jogos com a melhor média de avaliações (neste caso só entrarão na lista jogos com pelo menos 4 avaliações)
    4. 3 categorias que receberam o maior número de avaliações

### Requisitos não funcionais
