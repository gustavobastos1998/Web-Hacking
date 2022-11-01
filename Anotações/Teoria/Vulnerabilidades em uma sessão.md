## Sessão segura possui...

   - Limitação por sessão única: cada código deve ser válido até a sessão ser fechada.

   - Limitação por tempo: deve ter uma limitação de tempo, depois de expirar o tempo, um novo código randômico deve ser gerado.

   - Randômico: gerar sessão randomicamente, sem padrões.


## Más práticas de segurança referente à sessão

   - Enviar número de sessão pela url

   - Armazenar dados da sessão no client side

   - localStorage e sessionStorage (html5 storage). 
   
   - Caso uma sessão seja salva no localstorage, e o usuário não apague ou feche o navegador, isso pode atrapalhar as boas práticas de uma sessão segura, tendo em vista que a limitação por tempo foi violada ou a sessão única. 

   - O SessionStorage é destruído apenas quando o navegador é fechado. É salvo um token no computador e só será destruído caso o browser seja finalizado. Isso também dificulta para o server side controlar o tempo ou o uso do token. 