# DevSecOps

## DevOps



## Conceitos
- *Security by design*: modelar software com estratégias de negócio e esquemas que incentivem a segurança.
- *Shift Left / Secure Software Development*: implementar a segurança desde a primeira linha de código.


## Testes automatizados de Segurança de Aplicação:
### Static Application Security Testing(SAST)
Testes de caixa branca que analisam código a procura de padrões e trechos de código perigosos. Infelizmente costuma causar muitos falsos positivos e nem sempre é claro o bastante no feedback para ajudar o desenvolvedor a consertar o erro, causando frustração.

Exemplo de ferramentas: SonarCloud

### Dynamic Application Security Testing(DAST)
Testes de caixa preta que costumam analisar os comportamentos da aplicação. Busca erros comportamentais e ações suspeitas na aplicação.

Exemplo: Burp Suite, OWASP ZAP

### Infrastructure Application Security Testing(IAST)
Combinação do SAST e DAST e uma única ferramenta.

## Runtime Application Self Protection (RASP)

## Software Compose Analysis (SCA)
Analisa as tecnologias que o sistema emprega no projeto, cehcando as dependências e suas licenças e políticas de compliance. É importante para usar software com as devidas autorizações e entender a real composição de uma biblioteca.

Ficou bem famoso após a vulnerabilidade do *log4j*, porque muitos nem que os seus projetos usavam *log4j*. O que acontecia era que eles usavam uma biblioteca que usava outra biblioteca que por fim usava lof4j.


##