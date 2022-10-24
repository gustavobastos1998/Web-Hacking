## O que é?

   - Ferramenta extremamente importante para testes de sql injection. Utiliza payload prontos para atacar uma url especificada. 


## Utilidade

   - Ótimo para automatizar o processo de SQL Injection. 


## Flags

   - --cookie="COOKIE;"  ::  basta acessar a página e inspecionar o elemento, na parte de network pode ser pegos os cookies necessários.

   - -T <nome_tabela>  ::  procurar por uma tabela específica.

   - --dump  ::  muito útil para ser utilizado em conjunto do -T, para trazer todas as informações da tabela.

   - -u <URL>  ::  informa a url onde acontecerá o ataque.

   - --tables  ::  enumera todas as tabelas de todos os bancos de dados.


## Observações

   - Não utilizar caso não tenha autorização, pois pode derrubar o banco de dados e o ip da sua máquina é facilmente rastreável, caso não esteja usando algo para não deixar rastros, como por exemplo o navegador Tor e o sqlmap trabalhando juntos. 