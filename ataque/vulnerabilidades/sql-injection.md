# SQL Injection

SQL é uma lingaugem declarativa de manipulação de banco de dados, muito utilizada por sistemas gerenciadores de bancos de dados (SGBDs). Normalmente SGBDs recebem comandos SQL através de puro texto e isso é perigoso, porque se o programador de um website ou aplicativo com bancos de dados não tratar os inputs do ususário, é possível que os usuários tenham contato direto com consultas em seu SGBD.

Por exemplo, um campo de login precisa ser passado para um SGBD a fim de ter acesso à base de usuários e autenticar o usuário. Pense que o programador usou a seguinte estrutura de comando:

```js
SGBD.new_query("
    SELECT name, password
    FROM USERS
    WHERE name='" + login_field.name + "'
    AND password='"+ login_field.password +"';
");
```