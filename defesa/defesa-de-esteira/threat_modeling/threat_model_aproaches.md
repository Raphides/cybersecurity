# Abordagens de Modelagem de Ameaça

Existem várias abordagens para começar a modelar ameaças. As diferentes metologias utilizadas no mercado para modelar ameaças seguem algumas dessas abordagens e assim listam passo a passo do que fazer para modelar ameaças em seu projeto.

Em geral, são 3 abordagens:
- Centrada em Aplicação
- Centrada em Ativos/Risco
- Centrada em Ataques

## Modelagem Centrada em Aplicação
Público-Alvo envolvido: time de desenvolvedores.

1. Compreenda e visualize a aplicação na qual você está trabalhando. Como resultado, crie um Diagrama de Fluxo de Dados
2. Liste ameaças para cada elemento do DFD a partir de um Modelo de Classificação de Ameaças.

3. Ranqueie cada ameaça com base no Modelo de Classificação de Ameaças.

**Modelos de Classificação de Ameaças** são modelos que determinam quais lugares/momentos/sistemas são sucetívies a quais ameaças. Exemplos: STRIDE, Owasp Top 10.

- Benefícios
    - Garante um entendimento comum do funcionamento da aplicação.
    - Gera maior compartilhamento de conhecimento.
- Desvantagens
    - Necessita boa documentação.
    - Pode ser difícil de abstrair ameaças a partir a aplicação.
    - Pode ser difícil de perceber bugs e vulnerabilidades de uma aplicação que você mesmo contruiu.


## Modelagem Centrada em Ativos/Risco
Público-Alvo envolvido: stakeholders.

1. Crie uma lista de ativos.
2. Compreenda cada ativo e como eles funcionam no sistema. Como resultado, produza um Diagrama de Fluxo de Dados
3. Para cada ativo, procure ameaças que possam atingi-lo.

- Benefícios
    - Quando a equipe já conhece os ativos, essa abordagem acaba sendo o caminho mais natural a se seguir.
    - Os ativos estão sempre em foco. Dessa forma sempre sabemos o que temos que proteger, tornando essa abordagem mais objetiva para pessoas menos técnicas.
    - Mais compreensível e amigável para pessoas próximas ao negócio.
    - Útil para quando se faz auditorias de avaliação de riscos
    
- Malefícios
    - Pode ser complicado traduzir ativos para os componentes de Diagramas de Fluxos de Dados.
    - Pode ser complicado extrair ameaças dos ativos.
    - Ao focarmos nos ativos, o entendimento do sistema da aplicação em si fica em segundo plano. Como muitas ameaças da modelagem de ameaças de um sistema aparecem principalmente sobre aspectos técnicos, isso pode atrasar a modelagem em si.

## Modelagem Centrada em Ameaças
Público-Alvo envolvido: pentesters

1. Criar uma lista de atores de ameaças com seus:
    - motivos;
    - recursos; e
    - possíveis ataques
2. A partir do passo anterior, já é possível extrair uma lista de ameaças.

- Benefícios
    - Torna os ataques mais visíveis e explicáveis.
    - Pode ser divertido de produzir. 
- Malefícios
    - Extremamente enviesado.
    - Pode gerar cenários de ameaças pouco práticos, mais parecidos com filmes.
    - Necessita de pessoas com conhecimento em segurança de aplicações. A falta de pessoas com o conhecimento pode gerar cenários de ameaça faltando.