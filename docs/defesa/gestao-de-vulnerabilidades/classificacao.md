# Classificação


## As várias perspectivas de classificação de vulnerabilidades

O processo ideal de classificação é algo particular de cada contexto. Enquanto há modelos que veremos mais à frente que ajudam a classificar, ranquear e priorizarEnquanto os mais interessantes seriam aqueles que refletem o risco, u

```
Risco(ameaça, vulnerabilidade, impacto)
```

## CISA KEV
- Classificação que reflete a Ameaça
- oferece uma lista de vulnerabilidades amplamente exploradas nas agências federais do EUA.
- só olha para o contexto de agências federais dos EUA.
- só olha para o passado, para vulnerabilidades que já foram ou estão sendo amplamente exploradas no contexto.

## CVSS
- Classificação que reflete o Vulnerabilidade



## EPSS
- Classificação da perspectiva da Ameaça + Vulnerabilidade
- Modelo de classificação de código aberto.
- Vai de 0,00 a 1,00.
- Olha principalmente para o futuro, calculando e listando quais vulnerabilidades provavelmente serão exploradas daqui até 30 dias.
- É fácil de consultar o EPSS de vulnerabilidades. É listado o EPSS de todas as vulnerabilidades já encontradas.
- É fácil de calcular o EPSS de vulnerabilidades novas ou internas. O cálculo é simples.

## SSVC
- Classificação que reflete o Risco(ameaça, vulnerabilidade, impacto)
- Modelo de classificação de código aberto.
- Cria uma árvore de decisão para calcular o impacto.
- Como resultado, pode dar os seguintes resultados:
    - Defer
    - Scheduled
    - Out of Cycle
    - Immediate.
- Difícil de consultar e calcular SSVC de vulnerabilides já existentes e novas. É um processo complexo, por isso é pouco usado.
- A vantagem é que o conceito e perspectiva de risco é global, entendida não só pela TI, mas também pelos responsáveis pelo negócio.

## VPR
- 
- Modelo de classificação de código fechado da Tenable.