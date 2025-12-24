# Estratégias e termos comuns de ataques em vulnerabilidades

## "Vulnerabilidade"

"Uma instância de uma ou mais fraquezas em um produto que possa ser *exploited* (explorada), causando um impacto negativo a Confidencialidade, Integridade ou Disponibilidade (CID)" (CVE, 2025)

"Uma série de condições ou comportamentos que permitem a violação de uma política de segurança explícita ou implícita". (CVE, 2025)

"Fraqueza em um sistema de informação, procedimento de segurança de sistema, controle interno ou implementação que pode ser explorado ou acionado por uma fonte de ameaça. Nota: O termo fraqueza é sinônimo de deficiência. A fraqueza pode resultar em segurança e/ou riscos de privacidade." (CISA, 2025)

Referência:
- https://www.cve.org/ResourcesSupport/Glossary?activeTerm=glossaryVulnerability
- https://csrc.nist.gov/glossary/term/vulnerability

## "CVE" (Common Vulnerability Enumeration)

https://www.cve.org/About/Overview

## Execução de código arbitrário
Código arbitrário é "qualquer código" e para um atacante, executar código arbitrário significa ter a capacidade de executar qualquer script malicioso. Ter esse poder é extremamente preocupante. Muitas das vulnerabilidades a serem vistas só são possíveis por causa da execução de código arbitrário. Outras buscam melhorar a capacidade de código arbitrário ao atacante, permitindo diferentes linguagens de programação a serem executadas (por exemplo). O termo é extensamente utilizado pela comunidade de segurança cibernética.

Saiba mais:
- https://pt.wikipedia.org/wiki/C%C3%B3digo_arbitr%C3%A1rio

## Injeção de código
Quando um aplicativo permite a execução de código arbitrário por atores indesejados, pode ser possível realizar injeções de código para explorar a execução de código arbitrário. Injdeção de código significa injetar códigos/dados maliciosos no sistema para modificar o comportamento de algum programa ou processo sendo executado ou a ser executado é uma abordagem de ataque comum. Há várias vulnerabilidades que permitem ataques de injeção, alguns sendo simples de se aprender e replicar, outros exigindo muito conhecimento de computação. Apesar da curva de aprendizado variável, ataques de injeção de código não só são comuns, como perigosos.

## RCE
Execução de código remoto é a capacidade de executar código arbitrário na máquina de uma vítima através de uma conexão remota. Muitas são as vulnerabilidades que permitem RCE.


NOTA: execução de código arbitrário pode acontecer sem injeção de código. 

## DLL
DLL(*Dynamic Link Library*) é a biblioteca dinâmica* gerada por um código em C/C++ para o Windows. Em C, ao compilar vários arquivos ".c", um executável independente é criado como resultado. O mesmo acontece ao adicionar bibliotecas estáticas. Entretanto, ao compilar com bibliotecas dinâmicas, o executável se torna dependente da DLL, tentando se conectar a ela toda vez que for executado e executando o código dentro dela.

NOTA(*): Quando o assunto é linux, a biblioteca dinâmica gerada é chamada de objeto compartilhado e recebe a extensão SO (Shared Object). É muito mais comum explorar DLLs do que SOs.

## Overflow
Toda estrutura de dados num sistema possui um intervalo de valores possíveis de representar. Enquanto ideias e conceitos podem ter possibilidades infinitas de valores, estruturas de dados em sistemas têm um tamanho finito e portanto um limite do quanto conseguem representar através dos seus dados. Quando o valor a ser armazenado excede o quanto sua respectiva estrutura de dados consegue representar, ocorre um *overflow*.