## O que é?

   - É uma requisição forjada entre sites.


## Funcionalidade

   - Exemplo: um site qualquer com essa vulnerabilidade pode enviar uma requisição pro facebook mudando a senha do usuário, caso ele esteja logado, pois o cookie é necessário para fazer o POST. 


## Proteção contra CSRF

   - token: número aleatório, enviado junto da requisição. Número válido por sessão ou requisição, impedindo que o atacante use o token no formulário que ele está montando. 