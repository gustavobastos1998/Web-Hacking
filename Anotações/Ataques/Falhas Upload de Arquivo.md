## Como funciona

   - Em campos que possa ser feito upload pode-se subir arquivos maliciosos que dão acesso ao shell da aplicação. 

   - Nesse tipo de ataque, conseguimos fazer com que o back-end salve arquivos que passamos como parâmetro.


## Mitigar o ataque

   - O back-end pode tratar esse arquivo que foi enviado. 

   - Caso seja uma imagem, ele testa a extensão do arquivo para checar se é o mesmo tipo. Pode checar também tamanho, não permitindo arquivos grandes.