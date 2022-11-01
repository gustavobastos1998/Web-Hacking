## Tipos de falhas que levam ao roube de sessão

   - XSS: leitura e envio de cookie via javascript.

   - packet sniffing: leitura de pacotes de rede em texto claro (http).

   - exploit server: conseguir acesso no servidor e ler os arquivos.

   - browser history: ver histórico de navegação e sessões via url.


## Prevenções contra ataques

   - httpOnly Flag: bloqueia a leitura dos cookies via javascript. O ZAP indica caso uma request não apresente essa flag. 

   - Armazenamento seguro de sessões: local diferente do padrão, armazenamento em DBS. 

   - Criptografia (https): impede a leitura dos dados por programas como wireshark. https é recurso fundamental de segurança para qualquer aplicação web. 