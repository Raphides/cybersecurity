# Introdução a Modelagem de Ameaças
## O que é Modelagem de Ameaças

Com a grande quantidade de ameaças e vulnerabilidades, às vezes é difícil introduzir a segurança a aplicações. É difícil saber por onde começar, o que priorizar e como executar as prevenções e proteções. É nesse contexto de dificuldade que entra a modelagem de ameaças.

**Modelagem de ameaças é o processo sistemático e repetitivo de identificar e classificar as possíveis vulnerabilidades e ameaças de um software a serem exploradas.**

Ela segue uma abordagem de segurança proativa ao possibilitar que desenvolvedores descubram e avaliem vulnerabilidades e ameaças antes que elas aconteçam. É diferente da segurança reativa, a qual as ameaças devem primeiro ser exploradas para depois avaliá-las e mitigá-las.

Sua característica sistemática e procedural o permite ser integrado a esteiras e ciclos de desenvolvimento de desenvolvimento de software. Em relação a implementação da modelagem de ameaças nesse contexto:
- É melhor empregado **durante a elaboração de requisitos e design de um produto**. O quanto antes do lançamento, melhor, permitindo aos desenvolvedores aproveitar mais a característica proativa da modelagem. 
- Em ciclos e metodologias ágeis, os requisitos e design do produto podem mudar. Por isso, a **modelagem de ameaças deve ser repetida a cada iteração** para se manter atualizada a realidade do projeto.
- A partir do processo de modelagem de ameaças, pode-se inferir requisitos de segurança.


## O processo em si

Como já foi dito anteriormente, a modelagem de ameaças é um processo sistemático. Há diversas maneiras de realizá-la, mas alguns aspectos são presentes em quaisquer modelagem de ameaças:

- Como input, toda modelagem de ameaças precisa ao menos do entendimento e funcionamento da aplicação/solução. Por isso é interessante que stakeholders e/ou desenvolvedores estejam presentes durante a elaboração da modelagem de ameaças.

- Como output, a modelagem de ameaças sempre busca entregar uma lista de ameaças que podem ser exploradas no software e ranqueadas por relevância e facilidades.

- Artefatos comuns envolvidos:
    - Diagrama de Fluxo de Dados (DFD)
    - Lista de ameaças e vulnerabilidades
    - Ranqueamento de ameaças e vulnerabildiades.

O processo em si de todo processo de modelagem de ameaças recai sobre as seguintes etapas:


1. **Decidir o escopo**, quanto do software será incluído na modelagem, quais regulações e políticas de segurança devem ou não devem ser consideradas.
2. **Analisar o Alvo**, normalmente sendo  acompanhado da criação do *Diagrama de Fluxo de Dados* (DFD).
3. **Identificar e Enumerar as ameaças**
4. **Classificar as ameaças**

Mais etapas, como **enumerar meios de mitigação** e **criar avaliações** de risco podem ser incluídas nesse processo, mas normalmente são mais associadas a processos de **Análise de Ameaça**, diferentes dos processos de Modelagem de Ameaças. Infelizmente, isso não impede que em situações reais, empresas peçam Modelagem de Ameaça esperando também Análise de Ameaça.


## Índice
À seguir, há o índice dos conteúdos a serem aprofundados no assunto *Modelagem de Ameaças*.

2. Abordagens
    - Centrado em Aplicação
    - Centrado em Ativos
    - Centrado em Ataques
3. Diagrama de Fluxo de Dados
4. Metodologias
    - PASTA
    - Microsoft Threat Modeling
    - TRIKE
    - OCTAVE
    - VAST
    - LINNDUN
5. Modelos de Enumeração e Classificação de Ameaças
    - STRIDE
    - Bibliotecas de Ataque
    - Árvores de Ataque
6. Modelos de Ranqueamento de Ameaças
    - CVSS
    - CWSS