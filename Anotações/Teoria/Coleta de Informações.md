## Coleta Ativa x Passiva

   - A coleta ativa se refere a comunicação direta com o alvo. Isso é um problema, pois seu acesso é registrado nos logs dos servers, e caso suas ações sejam barulhentas como o nmap é possível que o servidor bloqueie pacotes para sua máquina. Raro acontecer isso, mas é importante se atentar a isso.

   - A coleta passiva busca dados do alvo em lugares públicos, como a internet. Whois é uma ferramenta interessante para coletar informações de quem registrou o domínio ou subdomínios, informações de endereços de email sem se conectar com o alvo. É uma maneira mais discreta de coletar informações, já que a comunicação não é com o servidor, portanto ele não saberá que essas informações estão sendo coletadas. 


## Que informações coletar?

   - *subdomínios*  :  pode mostrar servidores ocultos, que interagem diretamente com a aplicação principal.
   - *endereços ips*  :  de servidores, de banco de dados, de outras aplicações diretamente ligadas à principal.
   - *servidores DNS*
   - *endereços de email*  :  ajuda no ataque de força bruta.
   - *portas abertas(serviços)*
   - *sistemas operacionais*  :  importante para explorar falhas nesse SO.


## Whois

   - Ferramenta muito importante para coleta de informações. Consulta dados do alvo. Site utilizado: https://registro.br/tecnologia/ferramentas/whois/

   - O kali linux já vem com o whois instalado. 


## Observações

   - A coleta de informações deve ser feita SEMPRE. É uma etapa muito importante e não deve ser menosprezada. Imprescindível para a criação do relatório. 

   - Importante colocar o resultado das informações em arquivos e armazená-los, para evitar ter que rodar o comando diversas veses. Como o nmap faz um scan nos serviços de uma aplicação web, é preciso internet para isso, podendo levar um bom tempo para terminar o comando.

   - MUITO IMPORTANTE, COM AS INFORMAÇÕES COLETADAS PELAS FERRAMENTAS ESTUDADAS, APLICAR O NMAP, DIRB, OWASP ZAP, GOOGLE HACKING NAS NOVAS INFORMAÇÕES ENCONTRADAS DURANTE O PROCESSO DE COLETA DE INFORMAÇÕES. EXEMPLO: APLICAR NMAP EM DOMÍNIOS E SUBDOMÍNIOS ENCONTRADOS PELO DIRB E SUBLIST3R, RESPECTIVAMENTE.