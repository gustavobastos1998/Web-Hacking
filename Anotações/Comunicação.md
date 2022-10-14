## Comunicação passo a passo

## Modelo TCP-IP
   
   - Computadores não conseguiam se comunicar antigamente, caso fossem de marcas diferentes.

   - Esse modelo veio para resolver esse problema.

   - Padrão simples e redundante para permitir a comunicação entre máquinas independente de seus modelos.

   - Dividido em camadas: 
      - Aplicação (http, ftp, ssh): responsável por cuidar dos dados enviadas pelo software e envia para a camada de transporte. 
      - Transporte (tcp e udp): responsável pela entrega dos dados e envia para a camada de internet. 
      - Internet (ipv4 e ipv6): responsável pelo endereçamento e roteamento de pacotes e envia para a camada física. 
      - Física (ethernet, wifi): responsável pela transmissão, via satélite, wireless, cabo etc.

    
## Protocolo TCP (Transmission Control Protocol)

   - Protocolo da camada de transporte

   - Garante que os dados da aplicação, seja http, ftp ou ssh, cheguem ao seu destino de maneira segura. Essa maneira segura se refere a integridade dos pacotes, ou seja, caso o pacote se perca no caminho é dever desse protocolo informar o cliente sobre essa perda, fazendo uma nova requisição, caso os pacotes venham duplicados, caso o cliente esteja fazendo muitas requisições o TCP controla essa demanda diminuindo a quantidade. 

   - Basicamente o que ele faz é estabelecer a comunicação entre hosts e garantir a integridade dos pacotes. 

   - 3 Way HandShake : 
      - TCP SYN : o protocolo tcp manda uma requisição para o servidor pedindo para acessar uma de suas portas.
      - TCP SYN/ACK : o servidor responde o protocolo dizendo que sua porta está disponível ou não.
      - TCP ACK : caso esteja disponível, o protocolo TCP estabelece a comunicação do cliente ao servidor.


## Protocolo HTTP (HyperText Transfer Protocol)

   - Após as etapas do protocolo TCP, o protocolo HTTP faz um GET Request para o servidor web. 

   - O servidor responde com o HTTP Response. 

   - O servidor DNS é responsável por transformar o endereço da URL em um endereço IP. 

   ### Requisição (Request) HTTP

       - Campos mais importantes da request: 

       - GET / HTTP/1.1  :  verbo HTTP, caminho solicitado. Neste caso, solicita a pasta raiz do servidor web.

       - HOST: 192.168.200.5  :  HOST onde está sendo feito o request.

       - USER-AGENT: MOZILLA  :  navegador que está sendo utilizado para fazer a requisição. 

    ### Resposta (Response) HTTP

       - Campos mais comuns da response:

       - HTTP/1.1 200 OK  :  Versão do HTTP utilizada. Código de resposta da solicitação.

       - DATE: FRI, 04 JUN 2021 17:13:30 GMT  :  data e hora da resposta.

       - CONTENT-TYPE: TEXT/HTML; CHARSET=UTF-8  :  tipo de conteúdo enviado.

       - SERVER: APACHE/2.2.8(UBUNTU)  :  Servidor que está enviando a resposta, por questões de segurança, a maioria deles não informa. 

    ### Códigos HTTP

       - 100~199 : Respostas de informação

       - 200~299 : Respostas de sucesso. Código 200 é usado para confirmação da request (OK), código 201 informa que a requesição foi criada, utilizada no comando POST.

       - 300~399 : Redirecionamento. Por exemplo: código 301, movido permanente. Caso o acesso da página seja por HTTP ela pode ter um recurso para forçar o acesso por HTTPS, então a resposta do servidor é pelo código 301.

       - 400~499 : Respostas de erros do cliente. 404 código de página não encontrada, quando o usuário digita uma url errada.

       - 500~599 : Respostas de erros do servidor. 500 código de erro interno do servidor. 

    ### Verbo/Métodos HTTP

       - São ações que você tem na requisição HTTP. 

       - GET: Solicitar URL. 
       - POST: Enviar dados para o servidor.
       - HEAD
       - PUT
       - DELETE
       - CONNECT
       - OPTIONS
       - TRACE


## Protocolo HTTPS (HyperText Tranfer Protocol Secure)

   - Versão segura do HTTP. Encriptografa os dados que estão sendo transmitidos. 

   - TLS (Transport Layer Security)

   - Útil para proteger os dados durante a transmissão deles. HTTPS não protege contra XSS ou SQL injection. Além de esconder dados sensíveis para evitar pessoas que estão "farejando" a rede.


## Enconding

   - charset: conjunto de caracteres

   ### URLs Enconding

      - '#': separador de âncoras : %23 (código para utilizar em strings)

      - '?' : separador de query strings : %3F (código para utilizar em strings)

      - '&' : separador de elementos : %26 (código para utilizar em strings)

      - '+' : indica um espaço : %2B (código para utilizar em strings)

   - '&#60' equivale ao caracter '<' quando quiser utiliza-lo em um arquivo html.

   - '&#62' equivale ao caracter '>' quando quiser utiliza-lo em um arquivo html.

   - OBS: PARA QUE OS DOIS CARACTERES FUNCIONEM, É PRECISO UM ';' APÓS SEUS CÓDIGOS.