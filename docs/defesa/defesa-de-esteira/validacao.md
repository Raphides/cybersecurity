# Validação




## Validação de Entradas

Na segurança, a validação das entradas é essencial para evitar erros por entradas inesperadas. Entradas maliciosas podem gerar manipulação de recursos internos e gerar danos aos ativos. Exemplos de ataques decorrentes de validação precária são:
- SQL Injection
- XSS
- Outros tipos de manipulação

### Validação Sintática
Garante que os dados sigam a sintaxe correta. Exemplo: se eu espero letras, só devo aceitar letras, não números.

### Validação Semântica
Garante que o dado faz sentido. Exemplo: se eu pedir duas datas para um período, preciso garantir que a data final seja após a data inicial.

### Validação Allow List
Só aceita o que é permitido. Tudo fora do padrão é negado! Isso é deny by default e portanto é recomendado.

### Validação Deny List
Permite tudo, com exceção de padrões perigosos específico. Não recomendado.

## Validação Client Side
Valida no lado do cliente, antes mesmo de mandar aos servidores.

O usuário pode enviar os dados diretamente ao servidor, ultrapassando essa validação. Potanto essa validação serve somente para UX, não serve para segurança!

## Validação Server Side
Diferente da Client Side, essa é obrigatória em todos os casos. Como o usuário não pode mais