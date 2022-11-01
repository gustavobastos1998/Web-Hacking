## O que é owasp zap?

   - É um proxy, semelhante ao burpsuite. 

   - Interceptar requisições, modificar, verificar respostar. 

   - Analisa toda a requisição e resposta web passo a passo, como se fosse um debug de requisições e respostas web. 

   - Usado também para fazer scan, brute force em sites. 


## Manual Explore

   - Uma opção muito boa para enxergar as requisições e respostas passo a passo. 

   - Pode habilitar HUD no navegador. 

   - Ferramenta importante quando desejar explorar XSS em uma página. Teste de Fuzz é uma das funcionalidades do ZAP, útil para testar payloads de em páginas web.

   - Podemos selecionar na requisição HTTP os parâmetros que são passados pela URL e adionar o payload que for necessário. 


## Observações

   - Tomar cuidado com o site que está fazendo o teste. O ZAP é uma ferramenta de scan agressiva, só pode ser utilizada para sites que você tenha permissão de atacar.