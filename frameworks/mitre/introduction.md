# Introduction to MITRE ATT&CK

## O que é o ATT&CK?

É um framework com várias recursos para entender o **comportamento dos adversiários** e defender-se deles. Entre eles, estão:
- Base de dados/enciclopédia de ataques reais.
- Dissecação dos principais ataques e técnicas de cybersegurança.
- Mapeamento de ataques segundo a Matriz ATT&CK.

### Pirâmide da Dor (por David Bianco)
Em relação ao comportamento do atacante, a *pirâmide da dor* mapea o que é fácil e difícil do atacante mudar. Mudar o hash que ele usa ou o seu endereço de IP é fácil, mas mudar de ferramentas e artefatos da rede começa a ser mais difícil. Atacantes especializados são humanos iguais a nós, eles vão ter mais preguiça e dificuldade em realizar tarefas difíceis e demoradas, e é a partir desse princípio que o ATT&CK brilha. O framework lida com as TTPs, ou *Tatics, Techniques and Procedures* os elementos mais difíceis de serem mudados por um atacante.

![Pirâmide da Dor]()

### Matriz ATT&CK

- Táticas: os grandes objetivos por trás de cada sequência de ataquies. Representada na matriz pelos títulos das colunas.
- Técnicas: um detahamento de como as táticas foram atingidas. A estratégia por trás da tática. Representado pelas células da matriz.
- Procedimentos: detalhamento técnico para realizar a técnica e atingir o objetivo. Ao clicar em uma célula da matriz, ou seja, em uma técnica, vemos uma série de procedimentos possíveis para realizá-la.

Cada um elemento em cada um desses três níveis possui uma página web própria na enciclopédia do ATT&CK, com descrições, grupos que aplciaram, exemplos reais, *data sources* (áreas importantes para melhorar a fim de identificar o esses ataques), TTPs relacionadas, detecção, mitigação e referências.

### Casos de Uso

- Detecção de ameaças.
- Linguagem comum entre profissionais de Cybersegurança e consumidores dessa informação.
- Simulação de ataques.
- Mapeamento de ataques do Red Team.

## Como mapear um ataque para o ATT&CK?

0. Entender o ATT&CK
1. Identificar o comportamento do atacante.
2. Pesquisar sobre esse padrão de comportamento.
3. Traduzir o comportamento para uma tática do ATT&CK.
4. Entender quais técnicas se aplicam ao comportamento analisado.
5. Comparar os seus resultados com os de outros analistas.


## Reference
- *Using MITRE ATT&CK for Cyber Threat Intelligence Training* BY *Katie Nickels* and *Adam Pennington*.
