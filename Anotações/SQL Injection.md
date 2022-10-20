## Entendendo o SQL Injection

   - Inserir querys em campos vulneráveis com o intúito de acessar tabelas e colunas no banco de dados.

   - Campo de login é um possível contato com o back-end (DB), podendo testar o SQL Injection.


## Comandos sql

   - OR é muito utilizado por pentesters para buscar informações em banco de dados. Juntamente com '1' = '1', pois a query, independente de condições retornara as colunas selecionadas por que 1 é igual a 1. Exemplo: select * from table where username = "jorge" or '1' = '1';. Ou caso for num campo de busca ou de login: " UNION select...; " OR '1'='1';.

   - UNION, importante lembrar que o UNION exige que as duas pesquisas na query tenham a mesma quantidade de colunas. 