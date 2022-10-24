## Entendendo o SQL Injection

   - Inserir querys em campos vulneráveis com o intúito de acessar tabelas e colunas no banco de dados.

   - Campo de login é um possível contato com o back-end (DB), podendo testar o SQL Injection.


## Comandos sql

   - OR é muito utilizado por pentesters para buscar informações em banco de dados. Juntamente com '1' = '1', pois a query, independente de condições retornara as colunas selecionadas por que 1 é igual a 1. Exemplo: select * from table where username = "jorge" or '1' = '1'; 1' or 'A' = 'A. Ou caso for num campo de busca ou de login: " UNION select...; " OR '1'='1';.

   - UNION, importante lembrar que o UNION exige que as duas pesquisas na query tenham a mesma quantidade de colunas. 


## Encontrando falhas SQL Injection

   - Localizar entrada de dados. XSS e SQL Injection necessitam de interação com o servidor. 

   - Supor um SQL Query para login php. Importante estudar a formatação da comunicação entre o php e o banco de dados.

   - Modificar a query, utilizando aspas simples, aspas duplas, ponto e vírgula, sustenido (#). Inserir parâmetros que o sql aceita em sua formatação. 


## Tipos e objetivos do teste

   - Teste baseado em erro: é interessante tentar gerar um erro proposital de sintaxe, por exemplo, para ver se o site retorna o erro sql, podendo informar o banco utilizado, colunas de uma tabela. Não é comum as aplicações retornarem a mensagem de erro para o cliente. 

   - Teste booleano: inserir dado e verificar se é verdadeiro ou falso. 

   - Temos como objetivo entender a base de dados como um todo, que informações ela armazena, nome de colunas, tabelas. 


## SQL In-Band

   - Também conhecido como UNION-Based SQL. Utilização do UNION nas sql querys. 

   - O UNION é utilizado para fazer uma segunda query com a mesma quantidade de colunas que a primeira query. Pode ser utilizado para identificar o nome do banco de dados, de tabelas. 

   - Basta fazer uma query chutando o nome da tabela, caso o site retorne o erro para o cliente ele pode informar muitas coisas. 

   - Existe uma tabela comumente chamada de information_schema.columns que traz diversas informações importantes. Exemplo de utilização: 1' UNION SELECT table_name, column_name FROM information_schema.columns#, retorna o nome da tabela e o nome da coluna. 1' UNION SELECT @@Version, null pode informar a versão do banco de dados.


## SQL Blind

   - Vulnerabilidade mais comum no escopo de sql injection. 

   - Mais difícil de explorar essa vulnerabilidade, pois não há muitas informações que são retornadas para o cliente.


## Mitigando o SQL Injection

   - https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html

   - site ótimo que descreve em detalhes como se previnir do SQL Injection. 

   - Importante para hacker ético entender como preveni essa vulnerabilidade para saber como os sites seguros se protegem contra SQL Injection.