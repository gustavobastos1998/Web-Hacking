## Como funciona DoS (Denial of Service)

   - Tem como objetivo interromper o funcionamento de um serviço. 

   - DDoS - ataque DoS porém com múltiplas máquinas fazendo as requisições para o servidor.


## Tipos de DoS/DDoS

   - DoS não intencional: na maioria das vezes acontece por falta de processamento, memória ram ou falta de rede. O server teve uma sobrecarga de usuários utilizando, para resolver isso, basta comprar um servidor mais potente. Uma programação mal feita também pode ser motivo do serviço cair. 

   - Flood Attacks: envio de dados maior que a capacidade do server. O atacante pode fazer com que várias máquinas ao mesmo tempo façam requisições ao site derrubando-o. 

   - Slowloris: técnica antiga, abertura de várias conexões de maneira lenta.

   - Falhas na aplicação: erros de programação, falhas no servidor etc. 


## Como fazer DoS simples

   - O kali nativamente tem o hping3 que é utilizado para gerar pacotes e fazer requisições. 

   - Tendo isso em mente, podemos aproveitar para fazer uma quatidade absurda de requisições parando um serviço específico.

   - Comando hping3 simples para DoS: "hping3 -S -p 80 --flood <ip_alvo> -a <ip_source>". A flag '-S' estabelece uma conexão TCP SYN, a flag '-p' se refere a porta da aplicação que será feito a requisição, '--flood' para 'floodar' o site com requisições e a flag '-a' para especificar com qual máquina será feito essas requisições. Pode-se usar um ip não existente como parâmetro da flag '-a', assim o servidor demorará alguns segundos até fechar a requisição TCP, gerando uma grande quantidade de requisições com a flag --flood.