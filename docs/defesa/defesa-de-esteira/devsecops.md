# DevSecOps
Integrar os times de desenvolvimento, segurança e operação. Os 3 times devem trabalhar com sinergia para alcançar um produto de qualidade. DevSecOps é também uma mudança organizacional e cultural.

![]()

Realisticamente, a segurança normalmente é aplicada somente na operação, no final do desenvolvimento ou de forma reativa (reação a bugs encontrados).



Os seguintes movimentos/conceitos buscam a aplicação da segurança também em outras etapas do produto:
- *Security by design*: modelar software com estratégias de negócio e esquemas que incentivem a segurança.
- *Shift Left* / Deslocamento à Esqueda: a ideia é se deslocar a seguranimplementar a segurança desde as fases iniciais do produto. O m
- Secure Software Development Cycle (S-SDLC): estabelece um ciclo seguro de desenvolvimento de software, focando na segurança desde as fases iniciais do desenvolvimento.

Enquanto o desenvolvimento e a operação, os times tem uma posição específica no andamento dos produtos, a segurança idealmente deve atuar diretamente em todas as etapas do produto:
- Planejamento
-



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

Ficou bem famoso após a vulnerabilidade do *log4j*, porque muitos nem que os seus projetos usavam *log4j*. O que acontecia era que eles usavam uma biblioteca que usava outra biblioteca que por fim usava *log4j*.


##