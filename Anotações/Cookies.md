## O que são cookies?

   - Cookies são utilizados para facilitar e deixar de maneira mais prática o acesso a aplicações web. Pois, os cookies servem para manter a conexão entre clientes e servidor, caso tenha saído do site e queira voltar, o servidor web da aplicação tendo em sua posse o cookie daquele usuário, já entende essa request como válida.

   ### Estrutura do Cookie

      - *DOMAIN* : website só pode enviar as informaç~es de cookie para seu próprio domínio.
      - *EXPIRES* : define uma limitação de tempo para aquele cookie.
      - *PATH* : define quais urls daquele domínio é necessário enviar o cookie.
      - *CONTENT* : contêm diversos valores, no formato 'NAME=VALUE'
      - *HTTP ONLY FLAG* : flag de segurança, permite que o cookie seja enviado apenas pelo http.
      - *SECURE FLAG* : flag de segurança, força o navegador a enviar o cookie utilizando https.


## Cookies x Sessão

   - Os cookies ficam salvos no cliente, nesse caso no web browser já a sessão fica salvo no servidor. 

   - Para os servidores, os cookies são úteis por são atribuídos a clientes. Após a utilização pode ser que esse cookie seja destruído e quando esse user acessar novamente, outro cookie é gerado. Mas geralmente, o cookie é salvo em um arquivo ou DB do server.