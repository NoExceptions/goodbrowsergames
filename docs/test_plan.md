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
