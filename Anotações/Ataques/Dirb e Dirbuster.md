## O que são?

   - Ferramentas para brute force em urls.


## Como funcionam?

   - A partir de um arquivo, geralmente chamado de wordlist, as ferramentas buscam para um determinado domínio utilizando as palavras contidas neste arquivo.

   - Basicamente o que fazem é fazer requisições http GET nessas urls.

   - Após verificar todas as urls, a ferramenta informa as responses para cada url, dizendo o código, 200, 301, 404, 501.


## Dirb

   - Utilizado no terminal, nativo de kali linux. A sua utilização é simples: "dirb http://site.com wordlist.txt", fará requisições http para o site.com com as palavras especificadas na wordlist.


## Dirbuster

   - Funciona exatamente igual ao Dirb, porém exibe numa interface gráfica o resultado das requisições.


## Observações

   - Brute force pode ser utilizada além de urls, sendo útil para login em um site por exemplo.

   - A wordlist pode ser criada e passada como parâmetro, mas é muito mais eficiente e inteligente utilizar uma wordlist pronta da internet que terá palavras comumente utilizadas nas urls de sites.

   - Útil para mapear como a aplicação está sendo executada. 