## Entendendo o SQL Injection

   - Inserir querys em campos vulneráveis com o intúito de acessar tabelas e colunas no banco de dados.

   - Campo de login é um possível contato com o back-end (DB), podendo testar o SQL Injection.


## Comandos sql

   - OR é muito utilizado por pentesters para buscar informações em banco de dados. Juntamente com '1' = '1', pois a query, independente de condições retornara as colunas selecionadas por que 1 é igual a 1. Exemplo: select * from table where username = "jorge" or '1' = '1';. Ou caso for num campo de busca ou de login: " UNION select...; " OR '1'='1';.

   - UNION, importante lembrar que o UNION exige que as duas pesquisas na query tenham a mesma quantidade de colunas. 


## Encontrando falhas SQL Injection

   - Localizar entrada de dados. XSS e SQL Injection necessitam de interação com o servidor. 

   - Supor um SQL Query para login php. Importante estudar a formatação da comunicação entre o php e o banco de dados.

   - Modificar a query, utilizando aspas simples, aspas duplas, ponto e vírgula, sustenido (#). Inserir parâmetros que o sql aceita em sua formatação. 


## Tipos e objetivos do teste

   - Teste baseado em erro: é interessante tentar gerar um erro proposital de sintaxe, por exemplo, para ver se o site retorna o erro sql, podendo informar o banco utilizado, colunas de uma tabela. Não é comum as aplicações retornarem a mensagem de erro para o cliente. 

   - Teste booleano: inserir dado e verificar se é verdadeiro ou falso. 

   - Temos como objetivo entender a base de dados como um todo, que informações ela armazena, nome de colunas, tabelas. 