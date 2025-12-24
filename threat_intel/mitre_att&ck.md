# MITRE ATT&CK

## O que é o ATT&CK?

É um framework com várias recursos para entender o **comportamento dos adversiários** e defender-se deles. Entre eles, estão:
- Base de dados/enciclopédia de ataques reais.
- Dissecação dos principais ataques e técnicas de cybersegurança.
- Mapeamento de ataques segundo a Matriz ATT&CK.


### Pirâmide da Dor (por David Bianco)

Em relação ao comportamento do atacante, a *pirâmide da dor* mapea o que é fácil e difícil do atacante mudar. Mudar o hash que ele usa ou o seu endereço de IP é fácil, mas mudar de ferramentas e artefatos da rede começa a ser mais difícil. Atacantes especializados são humanos iguais a nós, eles vão ter mais preguiça e dificuldade em realizar tarefas difíceis e demoradas.

É a partir desse princípio que o ATT&CK foi criado. O framework lida com as TTPs, ou *Tatics, Techniques and Procedures* (TTPs) os elementos mais difíceis de serem mudados por um atacante.

![Pirâmide da Dor]()

### Estrutura da Matriz ATT&CK

- Táticas: os grandes objetivos por trás de cada sequência de ataquies. Representada na matriz pelos títulos das colunas.
- Técnicas: um detahamento de como as táticas foram atingidas. A estratégia por trás da tática. Representado pelas células da matriz.
- Procedimentos: detalhamento técnico para realizar a técnica e atingir o objetivo. Ao clicar em uma célula da matriz, ou seja, em uma técnica, vemos uma série de procedimentos possíveis para realizá-la.

Cada um elemento em cada um desses três níveis possui uma página web própria na enciclopédia do ATT&CK, com descrições, grupos que aplciaram, exemplos reais, *data sources* (áreas importantes para melhorar a fim de identificar o esses ataques), TTPs relacionadas, detecção, mitigação e referências.

### Casos de Uso

- Detecção de ameaças.
- Linguagem comum entre profissionais de Cybersegurança e consumidores dessa informação. A maior parte dos relatórios de ataques de cybersegurança utilizam termos específicos do MITRE ATT&CK.
- Simulação de ataques.
- Mapeamento de ataques do Red Team. A maior parte dos relatórios de ataque de cybersegurança mapeiam os ataques analisados via MITRE ATT&CK. 

### Como mapear um ataque para o ATT&CK?

0. Entender o ATT&CK
1. Identificar o comportamento do atacante.
2. Pesquisar sobre esse padrão de comportamento.
3. Traduzir o comportamento para uma tática do ATT&CK.
4. Entender quais técnicas se aplicam ao comportamento analisado.
5. Comparar os seus resultados com os de outros analistas.

### Reference
- *Using MITRE ATT&CK for Cyber Threat Intelligence Training* BY *Katie Nickels* and *Adam Pennington*.
---
## Reconhecimento (TA0043)

[Mais sobre essa tática](https://attack.mitre.org/tactics/TA0043)

Essa tática consiste na coleta de informações por parte do atacante que o auxiliem em sua ofensiva. Pode incluir desde informações do sistema em si até informações pessoais das vítimas.

---
Atacantes vão buscar informações sobre:
- Suas informações pessoais e privadas.
- Seu local de trabalho / estudo / atuação.
- Sua rede.
- Seus dispositivos.
- Sua atividade e presença online.

Através das seguintes fontes de informação:
- Fontes abertas
- Fontes fechadas

---

### Informações Úteis a Procurar
- Coletar Informações Pessoais da Vítima (T1589)
    - Endereços de Email (T1589.002).
    - Credenciais (T1589.001), como senhas, tokens, etc.
    - Nomes, CPFs, RGs.
    - Moradia.
    - Família.

- Coletar Informações sobre a Empresa em que a Vítima trabalha ()
    - Contexto Empresarial.
    - Locais físicos das filiais/uniadades.
    - Funionários e Cargos.
    - Horários e turnos de trabalho.

- Coletar Informação da Rede da Vítima ()
    - Propriedades de Domínios da Vítima (T1590.001) podem revelar dados básicos do domínio, dados administrativos, contatos, endereço comercial, nomes de servidores, etc.
    - Domain Name Server, ou DNS (T1590.002) podem revelar dados básicos do DNS, tecnologia do DNS, nome de servidores registrados, servidores de email e outros hosts.
    - Dependências confiáveis (T1590.003) do serviço da vítima podem revelar parceiros empresariais e serviços de terceiros em que a vítima confia, assim como seus respectivos domínios/IPs.
    - A topologia da rede (T1590.004) da vítima, ou seja, a infraestrutura da rede, condições do ambiente e detalhes dos dispositivos utilizados. Numa rede minimamente protegida, a topologia de dispositivos de defesa da rede (T1590.006) pode ser mapeada.
    - Endereços de IP (T1590.005) ou blocos / sequências deles. Sequências de IPs podem revelar dados como provável localização, tamanho da organização, provedor de internet e CDN.

- Coletar informações do Host (dispositivo conectado a rede):
    - Hardware (T1592.001 e T1592.004), como tipos e versões de componentes, componentes vulneráveis e componentes de segurança.
    - Software (T1592.002 e T1592.004), como tipos e versões de software, bibliotecas, sistema operacional, software vulnerávies e software de segurança.
    - Firmware (T1592.003 e T1592.004), como tipo e versão, configuração, propósito, vulnerabilidades e nível de segurança.

### Meios de Obtenção de Dados em Fontes Abertas 

- Mídias Sociais (T1593.001)
- Motores de Busca (T1593.002)
- Repositórios de Código (T1593.003)
    - Github
    - Gitlab
    - Bitbucket
    - SourceForge
- Websites da vítima (T1594)
- Implementações do Protocolo WHOIS (T1596.002). Exemplos:
    - [Whois.net](https://www.whois.net)
    - [Registro BR](https://registro.br/tecnologia/ferramentas/whois/)
    - [WHOIS da Hostinger](https://www.hostinger.com.br/whois)
- Certificados Digitais (T1596.003)
    - [SSL Checker](https://www.sslshopper.com/ssl-checker.html)
- Procura por atividades públicas de Domain Name System (DNS)(T1596.001), assim como possíveis vulnerabilidades. Registros de DNS podem revelar nomes de servidores de uma empresa.
    - [DNS Dumpster](https://dnsdumpster.com/)
    - [CIRCL Pasive DNS](https://www.circl.lu/services/passive-dns/)
- Dados e vulnerabilidades do serviço que é host do seu site, ou seja, do seu Content Delivery Network (CDN) (T1596.004).
- Escaneamentos Ativo e Não Ativo (T1595 e T1596.005).
    - Escaneamento de IP (T1595.001).
        - Ping e Traceroute
        - Shodan
        - NMAP
    - Escaneamento por Vulnerabilidades (T1595.002).
    - Escaneamento de infraestrutura por listas de palavras (T1595.003).
        - GoBuster
        - DirBuster
        - Dirb
        - [s3recon](https://github.com/clarketm/s3recon)
        - GCPBucketBrute
- Outros websites com informações da vítima.

### Meios de Obtenção de Dados em Fontes Fechadas

- Phishing (T1598) por informação. O pedido de informação em si pode vir através de:
    - Links (T1598.002)
    - Anexos (T1598.003)
    - Ferramentas de Terceiros, como mídias sociais e serviços de email (T1598.001).
    - Imitação por voz síncrona ou assíncrona (T1598.004).
    - Imitação por vídeo síncrono ou assíncrono.
- Bases de dados fechadas com informações técnicas relacionadas a vítima.
    - Sites de vazamento na internet ou darkweb.
- Venda de dados (legais e ilegais)
- Feeds de Inteligência (gratuitos e pagos)
    - [FBI Infraguard](https://www.infragard.org/)
    - [Abuse](https://abuse.ch/)
    - [Cisco Talos Intelligence](https://www.talosintelligence.com/)
    - Google Safe Browsing
    - [Spamhaus Project](https://www.spamhaus.org/)

## Movimentação Lateral (TA0008)

[Mais sobre essa tática](https://attack.mitre.org/tactics/TA0008)

Essa tática traduz as técnicas de atacantes para se mover através no seu ambiente. Ou seja, é como o atacante, após conseguir acesso ao sistmea, tenta conseguir acesso a outras contas e dispotivos na rede/ diretório ativo/ sistema.

### Internal Spearphishing
Ao roubar um endpoint do sistema, o atacante abusa da boa reputação que a conta roubada tem com outras contas do sistema para realizar ataques de phishing direcionados. Em ataques de phishing, o atacante persuade um usuário legítimo a realizar alguma ação não segura. A descrição refere-se a técnica *Internal Spearphishing (T1534)*.

Associações:
- Pode vir junto a técnica de Personificação

Exemplos de procedimentos para realizar um Internal Phishing:
- um atacante através de um email comprometido da empresa envia um arquivo anexado malicioso para um funcionário da empresa.
- um atacante através de um email comprometido da empresa envia um link malicioso para um funcionário da empresa.
- Arquivos falsos se fingindo de legítimos em pastas compartilhadas.

Previnir esse tipo de ataque é difícil. Ademais, sempre é importante concientizar usuários de sistemas obre phishing.

Detectar esse ataque pode ser feito a partir de:
- Análise de conteúdo de mensagens na rede/sistema em busca de links e anexos suspeitos. Seja por análise de rede ou por análise de logs.
- Análise do fluxo de rede para detectar spam interno, muitas vezes característico de Internal Spearphishing.


### Serviços Remotos

Serviços Remotos são bastante usados em empresas, principalmente quando se fala em datacenters. Serviços remotos são um dos potes de ouro da movimentação lateral e podem ser utilizados de diversas formas pelos atacantes para movimentação lateral.

Para começar, um atacante pode conseguir um acesso legítimo ao serviço remoto simplesmente em decorrência do dispotivo atacado já ter uma sessão aberta com esse serviço. Dessa forma, o atacante não necessita de saber as credenciais e têm acesso a outro dispositivo da empresa sem maiores dificuldades. Esse caso se refere a técnica *Roubo de Sessão de Serviços Remotos (T1563)*.

Caso não haja uma sessão aberta, o dispoitivo ainda pode ter acesso a conexão remota. O atacante pode usar credenciais válidas que ele pode ter adquirido de outra forma e criar uma nova sessão ao serviço remoto, tendo novamente acesso a outro dispositivo da empresa. Esse caso se refere a técnica *Serviços Remotos (T1021)*.

Mesmo que o atacante não roube uma sessão aberta ou tenha credenciais válidas, o atacante pode explorar vulnerabilidades de serviços remotos. Muitas vezes empresas não atualizam seus softwares direito, o que dá muita chance aos atacantes de explorar vulnerabilidades conhecidas. Essa é uma técnica bem comum para ganhar acesso a servidores, visto que sistemas como SSH, MySQL, RDP e SMB possuem vulnerabilidades bem conhecidas em suas versões menos recentes. Essa caso se refere a técnica *Exploração de Serviços Remotos (T1210)*.

Associações:
- Descoberta de Serviços de Rede ou qualquer outro método da tática de Descobrimento. Usado para descobrir se o sistema invadido possui alguma vulnerabilidade a ser explorada.
- Dependendo da criticidade da vulnerabilidade, pode virar uma Exploração para Escala de Privilégios.

Ferramentas:
- Empire Framework
- PoshC2 Framework
- net
- PsExec
- Cobalt Strike
- Brute Ratel C4
- Koadic Framework
- Pupy
- QuasarRAT



Exemplos de Procedimentos (T1210):
- Exploração da CVE-2020-1472, referente ao Windows Netlogon, para obter acesso aos servidores do Diretório Ativo do Windows.
- Uso da ferramenta Mimikatz para explorar a vulnerabilidade CVE-2020-1472, referente ao Controle de Domínio e noramlmente chamada de ZeroLogon.
-  Exploração de uma das várias vulnerabilidades de execução de código remoto em SMB.

Prevenção

Detecção


### Traferência Lateral de Ferramentas Maliciosas
Quando um atacante possui um dispositivo com acesso a uma rede interna ou acesso a outros dispositivos, ele pode tentar transferir ferramentas e malwares pela rede para conseguir comprometer mais dispositivos. O outro dispositivo pode receber essas ferramentas via email, pastas compartilhadas, repositórios compartilhados, mensagens, protocolos de transferência e serviços remotos. Essa descrição em geral se refere a técnica *Traferência Lateral de Ferramentas (T1570)*.

Quando essa transferência se dá através de meios físicos removíveis, como inserção de pendrives maliciosos em sistemas vítimas, nomeamos a técnica como *Replicação através de Dispositivo de Mídia Removível (T1091)*.

Existe a possibilidade da transferência em si não adicionar arquivos, mas modificar arquivos pré existentes, adicionando scripts e metadados maliciosos neles. Isso acontecendo em arquivos dentro de ambientes compartilhados caracteriza a técnica *Corromper Conteúdo Compartilhado (T1080)*.

Em casos mais específicos, o dispositivo roubado pode ter acesso a centros de gerenciamento e distribuição de software das empresa. O atacante poderia distribuir malware ou ferramentas maliciosas nos centros de distribuição de software ou poderia lançar atualizações maliciosas a todas as máquinas do ambiente. Esses casos mais específicos são referentes a ténica *Ferramentas de Entrega de Software (T1072)*.

Associações:
- Importação de Ferramentas
- Internal Spear Phishing

Ferramentas:
- CMD
- ftp
- PsExec
- esentutl
- Expand


Exemplos de Procedimentos:
- Um atacante pode inserir ferramentas maliciosas em pastas compartilhadas com outros usuários da rede interna.
- Malware pode ter a capacidade de se replicar através de serviços remotos utilizando SMB.


Detecção - Monitorar:
- Operações com arquivos
- Acesso ao compartilhamento de rede
- Tráfego de rede, contando o monitoramento do conteúdo e fluxo.
- Criação e agendamento de processos
- Execução de comandos.

Prevenção:
- Firewall.
- Adoção dos Sistemas de Detecção e Prevenção de Intrusões (IPS e IDS) baseados em assinatura.


### Uso de Material de Autenticação Alternativa

Quando se cria uma conta ou adentra em uma conta após ter feito login recentemente, é possível que o sistema não peça sua senha ou outro fator de autenticação. Isso é feito através de uma **autenticação alternativa**. É possível que uma máquina infectada possa utilizar-se dessa autenticação alternativa para ter acesso a outra conta/dispositivo, ação referente a técnica *Uso de Material de Autenticação Alternativa (T1550)*.

Antenticações alternativas podem ser realizadas através de diferentes sistemas e materiais. Cada um desses materiais caracteriza uma subtécnica da T1550.

|Material|Sub técnica vinculada|ID|Serviço Associado|
|-|-|-|-|
|Token de Acesso|Application Access Tokens|001|APIs, AWS, Oauth, Docker e muitos outros|
|Hash guardado da senha|Pass the Hash|002|Todos os sistemas de autenticação vulneráveis a captura / vazamento de hash |
|Ticket|Pass the Ticket|003|Todos os sistemas que usam o protocolo Kerberos. Exemplo: Windows|
|Cookie|Web Cookie Session|004|Web|

<br>


Associações:

Como a técnica exige que o atacante primeiro consiga o material de autenticação alternatica, muitos das técnicas associadas são parte da tática ***Acesso a Credencial***


Prevenção:
- Configuração decente das aplicações e diretórios ativos em relação a autenticação, gerenciamento de usuários e gerenciamento de usuários privilegiados.
- Exigir que o desenvolvedor estude e implemente estratégias de proteção de material de autenticação alternativo.
- Enrijecer e incentivar políticas de senhas seguras ao usuários e conscientização.

Detecção:
- Observar as características do sistema e conexão que estão usando as credenciais. De preferência, utilize os logs da aplicação/diretório ativo junto para identificar melhor irregularidades na conexão e login.

