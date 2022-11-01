## Autenticação via usuário e senha

   - Útil e prático para o usuário.

   - Porém, muito pouco seguro.

   - Existe a utilização de hashes para proteger as senhas dos usuários. Além delas, também há o chamado 'salt' que é adicionado à senha e criado o hash em cima da senha com o salt para aumentar o nível de segurança.

   - Autenticação de múltiplos fatores é comumente utilizado para aumentar a segurança também. 


## Vulnerabilidades da autenticação

   - Canal inseguro: caso o site utilize hhtp ao invés de https.

   - Políticas de senhas fracas: senhas simples e fáceis de serem quebradas. 

   - Armazenamento inseguro: senhas armazenadas em texto claro.

   - Vazamento de dados: senhas repetidas podem comprometer diferentes serviços web.


## Tipos de ataques contra senhas

   - Brute Force: tentativa de combinação de caracteres

   - Ataque de dicionário: utiliza palavras do dicionário (inglês, português etc). Mais rápido que o brute force, pois há uma diminuição das tentativas que terá que fazer. 

   - Ataque personalizado: informações personalizadas + brute force. Tentará utilizar informação do alvo específico para tentar quebrar a senha, exemplo: data de aniversário, nome do filho, time favorito etc.

   - Rainbow table: utilizado para quebrar hashes de senhas. 