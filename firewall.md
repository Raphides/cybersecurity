# Firewalls

Firewalls são sistemas que filtram o tráfico na rede.

## Características das regras de firewalls
A maioria dos firewalls são top-down, ou seja, aplicam as regras de cima das listas para baixo.

É normal as regras e políticas de firewall permitirem ou não a entrada de pacotes a partir de fontes, remetentes, conteúdo malicioso e outros parâmetros. Quando um firewall acusa o pacote de cair em uma dessas políticas, a regra pode estar configurada para gerar um:
- **Allow**: aceitar o pacote e notificar a fonte.
- **Deny**: recusar o pacote e notificar a fonte.
- **Drop**: recusar o pacote e não notificar a fonte. Ótimo para a segurança.

## Gerações
### 1ª geração - Firewall Original (1988)
Os primeiros firewalls atuam principalmente na camada 3 do Modelo OSI. Eles monitoram o tráfego de pacotes na rede, analisando de onde vieram e quais são os seus destinos. Esta análise é conhecida como **filtragem estática** e, por mais que não seja assim tão eficiente atualmente, ainda é bastante usado em firewalls simples e baratos atualmente.

Ao buscar sua origem e destino, firewalls checam os IPs e portas do pacote. Um servidor que busca receber emails dificilmente deve aceitar conexões em portas diferentes de protocolos de email por exemplo. Entretanto, esse tipo de firewall não inspeciona o conteúdo dos pacotes e, como sabemos, não é difícil mandar um vírus por email ou algum outro código malicioso por IPs e portas permitidas.

- Exemplo: IPChains

### 2ª geração - Stateful Firewall (anos 90)
Com essa geração, houve a criação firewalls de **filtragem dinâmica**. Esses firewalls possuem um registro de estados das conexões prévias, " lembrando-se dos seus erros e acertos e adaptando-se a partir disso.

De forma mais técnica, eles bloqueiam o tráfico da mesma forma que os firewalls originais, mas criam uma tabela de estados de conexões passadas e assim possuem a habildiade de atualizar suas próprias regras e políticas de segurança. Assim, protocolos e IPs podem ter suas políticas atualizadas se estiverem de acordo com o resto das políticas daquele firewall. Isso é uma interessante mudança, visto que é comum bloquear a maior parte das portas e IPs por padrão, o que em firewalls de 1ª geração, resultaria muitos pacotes legítimos bloqueados e constante atualização manual das políticas.

Esse firewall possui acesso as conexões em andamento e as que já passaram, atuando assim também na camada 4, possibilitando que bloqueie conexões que anteriormente foram permitidas, mas logo depois causaram problemas de serviço.

Por realizar maiores trabalhos, esse firewall demanda mais tempo em operação e mais recursos da rede.

- Exemplos: Netfilter / IPTables.

### 3ª geração - Proxy Firewall (1991)
Firewall e proxy são duas tecnologias de segurança diferentes, mas os firewalls de proxy combinam as duas funcionalidades, gerando um firewall muito mais eficiente.

Firewalls de proxy usam as funcionalidades dos firewalls anteriores, mas os combinam com servidor intermediário (proxy) que é responsável não só por interceptar as conexões, como também analisar seu conteúdo mais profundamente. A partir disso, os firewalls da 3ª geração atuam também na camada 7, identificando os seus diferentes procolos (HTTP, FTP, POP3), analisando-os com base em riscos conhecidos desses tipos de pacotes e então permitindo ou não a passagem do pacote. Por ser um proxy, estes firewalls usam o método NAT, mascarando os IPs do serviço a ser protegido, gerando ainda mai segurança e sigilo ao sistema.

Atualmente esse tipo de firewall vem evoluindo e ganhando mais destaque com o surgimento do ***Web Application Firewalls***(WAFs). WAFs são firewalls de proxy focados em conexões web (principalmente a HTTP), mas tem um foco em proteger empresas. Dessa forma, os WAFs vão funcionar principalmente como proxies-reversos, interceptando a informação do servidor (quem fornece a página web) ao invés do cliente (quem pede a página web).

### 4ª geração - Firewall estável e doméstica
- ***Next Generation Fiewall***  (NGFW): é um tipo de firewall atual que combina as tecnologias passadas de firewall com tecnologias anti-malware. Entre elas, estão antivirus, *Intrusion Prevention System *e *Intrusion Detection System.*
    - Exemplos:
- ***Unified Threat Management*** (UTM)
É um sistema que unifica várias soluções de seguranças comuns em mabvientes empresariais em um único software de gestão e visualização. Entre as soluções que mais fazem partes de UTMs, estão os: firewall, proxy, antivirus, antispam, etc.
    - Exemplos: 

## Componentes internos dos firewalls
As regras e políticas dos firewalls são organizadas em tabelas, cada uma com uma série de *chains* (divisão de políticas). As tabelas e regras a seguir são as existentes por padrão no firewall IPTables, mas outros firewalls podem possuir outros, além de alguns, como o NFTables, não serem entregues com nenhum.

### Chains
São locais onde as regras e políticas dos firewalls são armazenadas. Como listas. Fazem parte das tabelas de firewall.


- INPUT: conjunto de regras aplicadas a pacotes **entrando** do firewall, destinados a algum host da rede.
- OUTPUT: conjunto de regras aplicadas a pacotes **saindo** do firewall, **vindos de algum host da rede**.
- FORWARD: conjunto de regras aplicadas a pacotes **saindo** do firewall , mas **vindos de um host fora da rede**, ou seja, outra interface de placa de rede. Eles não tem nem fonte nem destino a nossa rede.
- PREPROCESSING: conjunto de regras aplicadas aos pacotes de firewall **antes de serem encaminhados**. É aqui que as regras de NAT para são armazenadas para **tradução de endereços de saída**, já que os pacotes vindos tem como destino o firewall.
- POSPROCESSING: conjunto de regras aplicadas aos pacotes de firewall **depois de serem encaminhados**. É aqui que as regras de NAT para são armazenadas para **tradução de endereços de entrada**, já que os pacotes vindos tem como endereço fonte os computadores reais na rede, o que deve ser trocado para o endereço do firewall no método NAT.

### Tabelas do IPTables
Firewalls como Iptables e afins possuem tabelas e chains pré-feitas, como:

#### Filters
Determina o conteúdo permitido. É também a tabela padrão.

Possui as chains:
- INPUT
- OUTPUT
- FOWARD

#### NAT
**Netword Adress Translator** é um método de tradução, representação e encaminhamento de uma série de IPs através de um único IP, o do proxy. Isso ajuda o proxy a ter as requisições sempre endereçadas a si.

A imagem a seguir mostra um modelo de proxy padrão.
```
Sendo A e B computadores da sua rede interna:


    A
    ^
    |
    v
Firewall <---> Internet
    ^
    |
    v
    B
```

As regras de aplicação do método NAT ficam armazenadas aqui.

Possui as chains:
- PREPROCESSING
- POSPROCESSING
- OUTPUT (para quando um pacote é criado no próprio firewall)


#### Raw
Responsável por mostrar exceções.

Possui as chains:
- PREROUTING
- OUTPUT


#### Security
Regras usadas para **controle de acesso e contexto**.

Possui as chains:
- INPUT
- OUTPUT
- FORWARD


#### Mangle
Configurações especiais de todas as chains.

Possui as chains:
- INPUT
- OUTPUT
- FORWARD
- PREPROCESSING
- POSPROCESSING

### Estrutura das regras
Toda regra está localizada em uma chain de uma tabela. Cada regra no IPtables é melhor disposta numa visualização estilo planilha com a seguinte estrutura:
- **num**: ordem da regra na fila do grupo chain-tabela específica.
- **target**: encaminha o firewall para a execução do *comando*(ACCEPT, DROP, etc) ou nome da regra descrita. Diferente do usual, o IPTables possui os seguintes comandos:
    - ACCEPT: o mesmo accept de sempre.
    - DROP: o mesmo drop de sempre.
    - QUEUE: envia a requisição para a userspace
    - RETURN: retorna para o processo principal.
- **prot**: protocolo em que a regra é aplicada.
- **opt**: opções especiais para a regra em específico. Se não houver, o padrão é `--`
- **source**: IP de origem do pacote
- **destination**: IP de destino do pacote.

