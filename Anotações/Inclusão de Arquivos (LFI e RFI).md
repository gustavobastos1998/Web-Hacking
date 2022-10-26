## Como ocorre essa falha?

   - Os parâmetros do back-end foram confgurados de maneira insegura.

   - LFI - Local File Include

   - RFI - Remote File Include


## Como identificar essa falha

   - Parecido com o PATH Transversal.

   - No php, os dois parâmetros que causam esse tipo de falha são: allow_url_include = off ; allow_url_fopen = off. 

   - Importante para o hacker analisar códigos de aplicação, caso tenha posse do php de uma página, para ver se esses parâmetros estam ligados, pois essa vulnerabilidade pode ser explorada. 


## Como efetuar o ataque

   - Basta criar um arquivo na pasta /var/www/html, subir um servidor web e enviar a url contendo o arquivo malicioso como parâmetro da página vulnerável. 

   - Importante lembrar que extensões php podem atrapalhar o processo, então é necessário escolher outras extensões.

   - Outra nota importante é ter a possibilidade de fazer um reverse shell com essa vulnerabilidade. Para isso, devemos criar uma conexão entre a máquina atacante e o server. 

   - No código do reverse shell, é necessário mudar o ip da máquina que estabelecerá a conexão e a porta que deverá estar aberta. Para isso, usamos o "sudo nc -lvnp <port_number>" com a mesma porta especificada no código.

   - Assim, quando executar a página com a url contendo o reverse shell, esse código será executado. No terminal onde o comando do netcat for executado, teremos acesso ao shell do servidor que foi estabelecido a conexão. 