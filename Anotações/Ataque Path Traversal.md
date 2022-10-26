## O que é?

   - Também conhecido como passagem de diretório.

   - Consiste em navegar pelas pastas da aplicação, tentando acessar arquivos na pasta raiz.

   - Esse ataque pode ser identificado observando a url. Caso a página passe como parâmetro pela url o arquivo, exemplo "?page=index.php", essa vulnerabilidade pode ser explorada.


## Ferramenta para automatizar esse ataque

   - https://github.com/wireghoul/dotdotpwn

   - feito o download do zip do github, basta extrair os arquivos, entrar na pasta que foi extraída e executar o dotdotpwn.pl