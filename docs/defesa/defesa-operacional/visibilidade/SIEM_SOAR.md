## Visibilidade Defensiva

## System Incident and Event Management (SIEM)

SIEM é um sistema de gerenciamento de eventos, principalmente de logs. Logs são registros de atividades e eventos em um sistema e são extremamente importantes por conferir autenticidade, não repúdio, comprovação, debugging e feedback. Perceba a quantidade de valores relacionados à segurança que um log trabalha, afirmando a importânica de sua análise para a sgurança de sistemas.

### Por que um SIEM?
Não basta só ler os logs? De fato logs normlamente são registrados de forma legível ou pelo menos com códigos não muito difíceis de entender. O problema dos logs é que os sistemas são aconeselhados a registrar muitos logs, já que nem sempre os desenvolvedores sabem quais logs serão essenciais. Muitas vezes, todos são essenciais. Não é posível ler tantos dados manualmente e torna-se necessário implementar plataformas e algorítmos para lidar com o Big Data dos logs. É aí que o SIEM entra.

### Funcionalidades do SIEM
- Armazena os logs dos mais diversos sistemas.
- Mostra os logs em um formato legível e de fácil entendimento aos seus operadores.
- Destaca a logs possivelmente perigosos.
- Relaciona logs de diferentes sistemas, facilitando a identificação das TTPs de um atacante.

Perceba como o SIEM, quando bem implementado, funcionará como uma ferramenta de **central de comando** dedicada a mostrar a visão geral do funcionamento da infraestrutura de TI da empresa. 

### O que um SIEM não faz
- Não gera de fato conclusões dos dados, ele só analisa e correlaciona. As conclusões devem ser tiradas pelo próprio operador do SIEM.
- Não gera respostas automáticas à possíveis ataques. É de responsabilidade do operador comunicar possíveis ameaças aos devidos operadores das outras ferramentas para acertar suas configurações de proteção. Por exemplo: um alerta de um SIEM não gera automaticamente uma mudança de políticas num firewall.

Em resumo, o SIEM não é uma ferramenta de automatização, é uma ferramenta de análise. É possível realizar respostas automáticas das correlações geradas pelo SIEM, automatizando seu processo? Atualmente é sim, mas com outra ferramenta chamada [SOAR]().

### Exemplos de SIEM mais utilizados no Brasil
- IBM Qradar (On Premise)
- Splunk SIEM (On Premise)
- Microsoft Sentinel (Cloud)
- Google Cronical (Cloud)

# SOAR