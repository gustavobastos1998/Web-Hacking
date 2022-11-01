## Como funciona?

   - Tenta vários usuários e senhas diferentes, utilizando uma wordlist com diversas possibilidades de sessão.


## Importância da coleta de informações

   - Importante passar por uma coleta de informação para ter uma facilidade extra nessa etapa.

   - Caso na coleta seja encontrado uma lista de emails de funcionários, ou nome deles, isso pode ser utilizado como wordlist para users no brute force.


## Hydra

   - Ferramenta de brute force. 

   - Há como especificar o tamanho da senha, os tipos dos caracteres, o usuário, a senha etc.

   - Detalhe: por segurança, é comum aplicações ter uma latência entre as requisições de login, ou seja, caso a quantidade de logins, com o mesmo usuário, seja vasta em pouco tempo, a própria aplicação não permite mais tentativas para o usuário específico.

   - A flag -t <number>, informa uma quantidade de requests feito para o url de tempos em tempos, tentando burlar essa vastas requisições. É comum utilizar o número 1, para fazer uma request de cada vez, pois por mais que seja mais demorado é mais seguro de funcionar, caso a aplicação após n tentativas não bloqueie a tentativa de login.


## XHydra

   - Versão do hydra com interface gráfica.


## Observações

   - O próprio kali, na pasta /usr/share/wordlists, apresenta diversas wordslists. Dentre elas as que o sqlmap usa, o dirb, nmap, john etc. O rockyou.txt.gz apresenta diversos passwords comuns que podem ser utilizados para brute force em senhas. Para extrair o arquivo, basta utilizar: "gunzip <arquivo.txt.gz>" ou "gzip -d <arquivo.txt.gz>".