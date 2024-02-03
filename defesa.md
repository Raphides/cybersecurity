# Defesa de segurança


## Antivirus
É um tipo de software comum e famoso usado para detectar e limpar malwares do seu computador. Utiliza principalmente Detecção por Assinatura ao escanear um arquivo, mas atualmente também usa alguns elementos de Detecção Heurística.
 
## Firewall
Firewall é um sistema clássico de controle de tráfego na rede. Ele intercepta o tráfego e libera ou não a passagem do pacote com base em uma série de *regras e políticas de firewalls* definidas pelo usuário. Essas regras, se bem feitas, podem garantir um alto nível de segurança a uma rede, tornando assim o firewall um sistema indispensável.

Marcas famosas de Firewall incluem *Palo Alto* com os seus NGFW.

## Proxy
Proxies são sistemas de interceptação de rede. Ao interceptarem de forma legal a conexão entre dois dispositivos, proxies podem realizar diversas ações antes de reencaminharem o pacote ao destino pretendido. Entre ela estão:
    - Debugging.
    - Análise de pacotes, parâmetros e payloads em busca de vulnerabilidades ou códigos maliciosos.
    - Mudança de conteúdo.
    - Mudança de IPs e outros parâmetros de cabeçalho de requisições.

Ferramentas como Burp Suite e OWASP Zap possuem *web proxies* (focados em requisições web) que interceptam requisições HTTP e copiam-nas para dentro do software, permitindo edição, reenvio, análise de vulnerabilidades, etc.

Firewalls mais recentes possuem proxies integrados a fim de inspectionar os pacotes de rede internamente e disponibilizar amis segurança em seus serviços.


## Web Application Firewall (WAF)
Diferente do que o seu nome sugere, o WAF é mais próximo de um proxy do que de um Firewall de fato. Um WAF intercepta o acesso a sites, principalmente aqueles 

Muito usado em empresas para limitar o acesso a sites maliciosos.

## IDS e IPS


Podem ser integrados a Firewalls.

## Desmilitarized Zone (DMZ)

A delimitação de ***zonas desmilitarizadas*** é uma prática que envolve a **segregação da rede** de um sistema em várias subredes, a fim de limitar que danos a uma determinda zona não se alastrem ao resto do sistema.

## Proteção de Endpoints e IoT
Envolvem: 
    - Proteção de Malware via AI.
    - Políticas de Uso do Dispositivo.
    - RBAC ou ABAC
    - Controle de Aplicação
    - Prevenção contra ataques zero-day.
    - Detecção de URL maliciosas e phishing.

### SIEM

Responsável por monitorar e analisar log de eventos a fim de detectar ***ofensas*** (possíveis eventos que podem gerar problemas de segurança).

Sistemas em serviço costumam gerar centenas de logs por dia dia, alguns esseciais para identificar e estudar possíveis tentivas de ataque. Como são centenas, é difícil analisar e correlacionar os diferentes logs dos diferentes sistemas e, para isso, existe o SIEM, capaz de juntar todos os logs em um mesmo lugar com uma linguagem e organização acessível aos profissionais de segurança e monitoramento de incidentes.

Sem o SIEM, podemos observar logs no Linux normalmente a partir do diretório /var/logs, mas ainda há outras fontes de logs de eventos que podem estar espalhados pelo sistema ou mal configurados.

Entretanto, uma das limitações do SIEM é a mesma de qualquer sistema de logs: muita informação e pouca ação. O SIEM não toma medidas de *hardening* e proteção do sistema. Mas ao menos o SIEM ajuda em interpretar e filtrar de fato os logs importantes para segurança.

Um produto SIEM bem popular é o IBM SIEM.

### SOAR

Como um grande orquestrador das ferramentas de respota a incidentes, o SOAR integra o SIEM e outras ferramentas para não só monitorar e analisar eventos que possam se tornar *ofensas*, como também orquestrar a tomada de medidas automatizadas para reagir a essas *ofensas*.

## EDR
Proteção que monitora os dispositivos de um cliente a fim de detectar possíveis ameaças e previnir infecções.

### XDR

Considerada a evolução dos EDRs.

### NDR

## Antispam

