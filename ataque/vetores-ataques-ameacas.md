# Vetores de ataque e ameaça

## Vetores de ataque

- **Acesso Direto**: dentro do ambiente da empresa, normalmente mitigado por segurança física e treinamento dos funcionários para servirem como monitoramento de comportamentos suspeitos ou não autorizados.
- **Acesso sem fio**: acesso ao ambiente de trabalho sem acesso direto ao maquinário. Pode ser mitigada através de VPNs, criptografia e trainamento dos funcionários para monitoramento de comportamentos suspeitos.
- **Email**: ataques de phishing, mitigado pelo treinamento contra phishing aos usuários. Algumas empresas também se esforçam para retirar phishings relacionados a sua imagem das redes sociais, conscientizando os usuários e funcionários.
- **Supply Chain/Cadeia de suprimentos**: ao invés de invadir uma empresa ou seu produto, hackers invadem a cadeia de suprimentos dela, ou seja, os produtos e empresas que servem a empresa alvo. Ataques que se aproveitam do "link fraco" da cadeia de suprimentos para inserir um malware através da cadeia são chamados de **downstream attacks**. Ataques assim são mais comuns de serem feitos por APTs e poem acabar tendo larga escala ao impactarem empresas e indivíduos diferentes. Para mitigar esses ataques, é necessário exigir medidas e posturas de segurança de toda a sua cadeia de produção. É comum utilizar os Service-Level Agreements (SLAs) para enforçar essas medidas.
- **Redes Sociais**: ataques de phishing, fake news (consenso de grupo), prova social, links malicioso. A mitigação normalmente está em treinar o usuário, mas limitar o acesso a redes sociais em ambientes de trabalho também pode ajudar. Algumas empresas também se esforçam para retirar phishings relacionados a sua imagem das redes sociais, conscientizando os usuários e funcionários.
- **Mídia Removível** (USB, CD, DVD, etc): malwares podem ser inseridos nessas mídas e compremeter os sistemas nos quais estão inseridos. A mitigação para ataques nesse vetor incluem políticas de grupo e da corporação para limitar o uso dessas mídias e tornar o usuário ciente disso. Treinar usuários aos perigos dessas mídias também é efetivo.
- **Cloud**: são alvos mais cobiçados, porque já são conhecidos por servir diversas outras empresas ([arquitetura *multi-tenancy*](https://medium.com/@edytarcio/arquitetura-multi-tenancy-bb7b47d7ba)). Os ataques mais conhecidos seriam negação de serviço (DDoS) e a mitigação dos ataques a esse vetor podem ser alcançados através de SLAs e exigência de avaliações de segurança aos serviços Clouds contratados.

## Vetores de Ameaça / Superfície de ataque

- **Baseado em Mensagens**: inclui emails, SMS, etc. Contém ataques de domínios comuns mal escritos, links maliciosos e arquivos maliciosos. É um vetor extremamente comum, principalmente por conta da estratégia de SPAM de enviar várias mensagens sem parar para vários destinos diferentes, esperando alguns poucos caírem no golpe. É dito que a maior parte das mensagens na internet é SPAM ou mensagem maliciosa. Atualmente as medidas de mitigação incluem o treinamento de usuários contra mensagens maliciosas e engenharia social, assim como o uso de ferramentas e técnicas de filtragem de SPAMs, estes eficientes em seu trabalho.
    
- **Baseado em Arquivos/Imagens**: malwares e código malicioso são adicionados a arquivos e imagens aparentemente legítimas. Isso ocorre através de vulnerabilidades e aberturas geradas pelo processamento, tratamento e exibição desses arquivos. Ataques comuns incluem a [esteganografia](../criptografia/intro#Esteganografia) (ocultar a existência dos dados malicioso no arquivo/imagem), *watering hole attacks* (injetar código malicioso em componentes de websites, aqui especificamente em arquivos/imagens desses websites, sendo mais comum em imagens) e código de execução remota (arquivos/imagens que quando executados permitem a execução de código remoto pelo atacante).

- **Baseado em Voz**: existem vários formatos de ataques que utilizam o áudio e voz como superfície de ataque. Atacantes podem capturar a voz de usuários para utilizá-las contra serviços que pedem autenticação ou autorização do usuário baseada por voz. Perguntas como "alguém está aí?" podem acompanhar um "sim" ou "não", respostas que podem ser capturadas e facilmente utilizadas para ataques. De forma mais sofisticada, atores maliciosos podem usar as respostas capturadas para trainar inteligências artificiais que replicam a voz.

- **Mídia Removível** (USB, CD, DVD, etc): malwares podem ser inseridos nessas mídas e compremeter os sistemas nos quais estão inseridos. A mitigação para ataques nesse vetor incluem políticas de grupo e da corporação para limitar o uso dessas mídias e tornar o usuário ciente disso. Treinar usuários aos perigos dessas mídias também é efetivo.

- **Software Vulnerável ou Não Suportados**: todo tipo de software, seja aqueles com interface visual; que agem sem agente, somente a partir de protocolos e sinais; etc. Softwares não suportados não costumam ser monitorados e atualizados, causando vulnerabilidades. Entretanto nem todo software vulnerável é não suportado. Esse tipo de vetor pode ser tratado via políticas de grupo. Outro ponto a ser destacado é como todo componente do software precisa ser verificado sobre vulnerabilidades e fraquezas, sejam as configurações (Misconfiguration), dependências (Supply Chain), mecanismos e protocolos (Software Vulnerável e Redes Inseguras). 

- **Redes Inseguras**: sejam redes ethernet, wi-fi, bluetooth, todas precisam ser mapeadas e isoladas propriamente, limitando seu acesso a partir de confiança (firewalls, mecanismos de autenticação, etc).

- **Misconfiguration / Configuração Fraca**: gera uma falsa sensação de segurança e um buraco (gaping hole) na seguraça. Pode ser mitigado através da criação de um padrão esperado para as configurações e segurança. Esse padrão esperado pode ser utilizado em auditorias de segurança periódicas no sistema e escaneamento de vulnerabilidades, outras mitigações prováveis para esse vetor.

    - **Contas Compartilhadas/Contas de Grupo**: vetor normalmente gerado por configurações fracas. Contas compartilhadas são uma má prática de segurança, porque podem invalidar a natureza de não repúdio das contas. Contas compartilhadas são utilizadas por vários usuários e portanto pode ser difícil provar que tal usuário de fato realizou certa ação.

    Entre algumas configurações fracas notáveis, estão:
    
    - Permissões pouco restritas;
    - Contas administrativas inseguras;
    - Tratamento de erros fraco, que exibe informações internas demais do sistema;
    - Protocolos inseguros, como aqueles sem criptografia; e
    - Configurações padrões, já que muitas possuem contas e senhas padões;
    - Portas e Serviços abertos.
- **Supply Chain/Cadeia de suprimentos**: ao invés de invadir uma empresa ou seu produto, hackers invadem a cadeia de suprimentos dela, ou seja, os produtos e empresas que servem a empresa alvo. É comum por exemplo atacar empresas de MSP (Managed Service Providers), já que elas servem vários clientes. Ataques que se aproveitam do "link fraco" da cadeia de suprimentos para inserir um malware através da cadeia são chamados de **downstream attacks**. Ataques assim são mais comuns de serem feitos por APTs e podem acabar tendo larga escala ao impactarem empresas e indivíduos diferentes. Para mitigar esses ataques, é necessário exigir medidas e posturas de segurança de toda a sua cadeia de produção. É comum utilizar os Service-Level Agreements (SLAs) para enforçar essas medidas.

- **Vetor humano**: ao utilizar o vetor humano, um ataque tenta se aproveitar da mente humana para lançar ataques, seja através de enganação, erros comuns ou só coleta de informações. É muito comum na área de segurança cibernética se referir ao vetor humano como o "elo mais fraco", pela quantidade de ataques que se aproveitam desse vetor e uma falta de controles para lidar com isso.

