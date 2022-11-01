## O que é um DNS (Domain Name Service)?

   - O DNS faz a tradução da url para IPv4. Quando um computador faz um acesso ao Facebook, por exemplo, o servidor DNS se preocupa em transformar a url no ip do facebook. 

   - Extremamente necessário, é mais fácil lembrar do nome do site do que o ip. 


## Informações que o DNS pode oferecer

   - Caso haja vulnerabilidade, o servidor DNS pode informar todo o mapeamento de uma rede do site. Como por exemplo, servidor destinado a DB, aplicação ou backup. 


## nslookup

   - nslookup é uma ferramenta comum ao Windows e ao Linux e utilizada para se obter informações sobre registros de DNS de um determinado domínio, host ou ip.

   - Para utilizar, basta digitar no terminal linux: nslookup e apertar enter. Feito isso, uma espécie de shell vai ser aberto e aí pode ser colocado os parâmetros que serão utilizados para fazer a pesquisa de informações. Exemplo: > set type=ns, setta o tipo de consulta com name server e após isso é informado o domínio a qual será feito a pesquisa (URL). O resultado será printado no terminal e com esse retorno, podemos scannear usando o nmap os name servers que foram retornados pelo nslookup. 


## dig

   - Funciona como o nslookup, mas é mais fácil de usar. Ele retorna informações sobre registro DNS de domínios. Pode especificar o tipo de consulta usando o flag -t <tipo_consulta>, mx para endereços de email, ns para name servers.

   - dig axfr <dominio> @<name_server>  ::  esse comando é útil para mapear toda a infraestrutura de um site. Podendo mostrar servidores internos que normalmente não seriam vistos de maneira convencional. Sites bem estruturados não cometem esse erro, mas como hacker ético, é preciso testar isso por causa de haver a possibilidade de existir essa falha. 


## Observação

   - Existe ferramenta online que faz essas consultas DNS, podendo usar os tipos de consultas por endereço de email, name server etc. https://www.mxtoolbox.com link para a ferramenta online.