## Resumo até aqui

   ### Infraestrutura da empresa

   - Portas abertas, ips.

   - Informações de servidores DNS, servidores de email.

   - Vulnerabilidades comuns e documentadas de uma versão do servidor, Apache por exemplo.

   - Informação de domínio, subdomínios. 


   ### Funcionalidades da aplicação

   - URLs e arquivos ocultos - Dirb.

   - Vulnerabilidades web - Nikto.

   - Headers e Respostas.

   - Fluxo lógico da aplicação.


## Mapeamento da página

   - Procurar por páginas de login e se dentro delas têm uma área destinada a membros ou administração. Páginas de blog.

   ### Perguntas interessantes para se fazer em páginas de blog

      - Acessível sem estar logado?

      - Interage com a base de dados? postar comentários em publicações são salvas em DB.

      - Acessa alguma aplicação de terceiros? js, css de outras páginas.

      - É possível fazer upload ou download de arquivos? upload de imagens em comentários.

      - Há alguma interação? formulários, pesquisa etc. Campos de pesquisas, comentários de blog, formulários. 

      - Exibe alguma mensagem de erro? mensagem de erro mysql, javascript.