# NMAP
Ferramenta intrusiva que mapeia uma rede-alvo. É muito usada e famosa, além de possuir muitas opções de configuração e personalização e mostrar muitas características de redes favoráveis a ataques.

**Cuidados:**
- Intrusivo: não deve ser feito sem autorização.
- Lento: demora muito para mapear tudo.
- Inseguro: ompletamente detectável o seu uso.

Para entender sempre mais sobre o *nmap*, use as opções de verbosidade. Há três opções:

|Nível|Detalhamento|Comando|
|-|-|-|
|1|Baixo|`-v`|
|2|Médio|`-vv`|
|3|Alto|`-vvv`|


## Mapeamento de portas e serviços

Use a opção `-sV` para mostrar as versões dos serviços.

### Mapear portas específicas

```bash
nmap -p <porta> # escaneia a 'porta' específica.
nmap -p- # escaneia todas as portas.
```
### Como o *nmap* pega o serviço e a versão?
Bastante precisa

1. Banner-Grabbing: captura o banner do serviço na conexão e adivinha o serviço a partir do padrão. Mas e se o banner tiver sido previamente modificado?
    - Mudar o banner e fechar portas e serviços desnecessários são procedimentos de hardening de qualquer servidor, ainda que muitos não os façam.
2. Checa se a estrutura das respostas corresponde ao padrão do serviço.
3. Faz alguns testes com outras requisições do padrão do serviço e versão correspondentes.

## Tipos de Scans
Os scans do *nmap* são feitas a partir da manipulação das requisições TCP e UDP. Dessa forma, podemos categorizá-las em vários tipos a partir do procedimento:

- Scans por TCP:
    - TCP Connect Scans (`-sT`)
    - SYN Half-Open Scans (`-sS`)
    - TCP NULL Scans (`-sN`)
    - TCP FIN Scans (`-sF`)
    - TCP XMAS Scans (`-sX`)
    - ICMP / ARP Scan
- Scans por UDP:
    - UDP Scans (`-sU`)

### TCP Connect Scan

É importante entender sobre o *TCP 3-Way handshake* antes de ler esta parte.

O TCP Connect Scan escaneia as portas TCP abertas e fechadas, realizando a cadeia completa do *TCP 3-way handshake*. Esse scan é o método padrão empregado ao *nmap* quando este é feito sem o de privilégios de administrador (sem *sudo*).


O scan descobre se uma porta está aberta ou fechada através ao mandar um SYN. Se a porta estiver:
- **aberta**, a conexão retornará um SYN + ACK. O scan marcará a porta como *aberta* e devolverá e terminará o *handshake* ao enviar um SYN.
- **fechada**, a conexão retornará uma mensagem de RST (*TCP Reset*), indicando ao *nmap* que a porta está *fechada*.
- **omitida por um firewall através da opção DROP**, a conexão não retornará nada. Com isso, o *nmap* vai classficar a porta como *filtrada*. Entretanto, um firewall com um REJECT que retorna um RST é bem fácil de configurar, até mesmo no IPTables.




### SYN Half-Open Scan - Modo discreto

Acontece através da distroção do *TCP 3-way Handshake*. A conexão é semelhante ao TCP Connect Scan, mas se diferencia em seu comportamento ao perceber uma conexão aberta.

Ao invés de mandar SYN, SYN + ACK, ACK, o sistema envia um SYN, recebe um SYN+ACK (em casos de conexões abertas) e omite seu funcionamento ao enviar um RST (*TCP Reset*) ao invés de ACK. Assim, indica ao sistema alvo que aquela conexão está fechada e que não recebeu o pacote, confundindo serviços de logs e identificação de incidentes.

Entre os motivos de usar o Syn Half-Open Scan, estão:
- Velocidade, já que termina o 3-Way Handshake ainda na segunda etapa 
- Ocultação, já que o conexões TCP normalmente são registradas somente após terminarem. Ao enviar um RST, é como se a conexão nem existisse, já que o RST significa "porta fechada".

Entretanto, também há desvantagens, como:
- Alguns serviços não reagem bem a um TCP 3-Way Handshake incompleto, podendo gerar até parada repentina.
- Necessária privilégios de administrador do atacante, já que há a criação de pacotes crus e personalizados.

É o método de conexão padrão realizada quando se executa um scan através de um usuário com privilégios de administrador (`sudo nmap`).

### UDP Scan

A conexão via UDP é bem mais lenta e difícil de escanear, visto que ela é feita sem mensagens de confirmação. O UDP é *sem estado*, o que o torna perfeito para situações em que precimos mais da quantidade e velocidade do que da qualdiade da informação.

O Scan de UDP no *nmap* é acontece com dois envios de pacotes UDP para uma porta. Se a porta estiver:
- **aberta**, ela não retornará nada aos dois envios do nmap. Pode aocntecer do sistema atacado devolver um UDP de resposta confirmando a conexão, mas isso não é tão comum. Quando é possível induzir o serviço a deolver esse UDP, o nmap o faz ao adicionar payloads na mensagem de envio. Muitas vezes o nmap não tem como identificar se a porta está filtrada por um firewall ou não, então marca a porta como *aberta | filtrada*
- **fechada**, é comum que a porta envie um ICMP (ping) de volta com a mensagem "porta não alcançável". É possível configurar o firewall para gerar um REJECT que devolva um ping também, então fique atento.

### NULL, FIN e XMAS Scan
Não são comums, mas tentam ser mais discretos do que o SYN Half-Open.

Todos os 3 tentam fugir do uso da bandeira SYN, já que muitos firewalls impedem a criação de novas conexões e o SYN serve justamente para isso.

O NULL Scan consiste em passar uma primeira mensagem TCP do 3-Way Handshake, mas sem argumentos, opções, bandeiras ou qualquer conteúdo. É especificado em normas técnicas que pedidos assim devem ter um retorn RST caso a porta esteja fechada.

Semelhante ao NULL, o FIN Scan ao invés de enviar uma mensagem nula de SYN pelo TCP, ele envia um TCP com "FIN". Enquanto o XMAS, envia um pacote mal formado com PSH, URG e FIN que se parecem com uma árvore de natal quando vistas pelo Wireshark.

Nem sempre funcionam, já que as tais normas técnicas nem sempre são seguidas. O Windows e a Cisco são exemplos dos sistemas que não os seguem. Além disso, sistemas de IDS sçao bons em edetectar esses tipos de Scan

### ICMP / ARP Scannning

O escaneamento ICMP é serve para estabelecer as primeiras conexões com o alvo e adquirir um mapa da estrutura da rede atacada, este sendo muito útil para ataques de caixa preta. Ela procura escanear os IPs com hosts ativos. A opção `-sn` pede ao nmap para não usar portas em geral, forçando o nmap a usar o protocolo ICMP (sem root) ou ARP (com root em uma rede local) para mapeamento de rede também. O escaneamento precisa de uma especificação do intervalo de IPs a serem testados, que podem ser especificados através da notação CIDR, em que todos os hosts da rede (ou subrede) serão testados.

```bash
nmap -sn <IP>/<mask>
```
É interessante notar que mesmo que nmap tente não escanear nenhuma porta, ele ainda vai ser obrigado a mandar requisições TCP para as portas 443 e/ou 80.


## Opções de visibilidade (-T)
|Opção|Rótulo|Velocidade|Visibilidade|
|-|-|-|-|
|-T0|Paranoico|Extremamente Lento|Semi Invisível|
|-T1|Discreto|Lento|Pouco Preocupante|
|-T2||-|-|
|-T3|Normal|Rápido|Visível|
|-T4|-|-|Completamente Visível|
|-T5|Agressivo|Pode ser DoS|Extremamente visível|

## Identificação de Sistema Operacional
Costuma ser **bastante precisa**, você pode pegar ela a partir do comando `-O`.


Para adquirir essa informação, o *nmap* pode, por exemplo, usar:
1. Diferenciação por Time-to-Live (TTL) de ping.
    - Linux: 128
    - Windows: 64

### Identificação das versões e distribuições
Para diferenciar o sistema operacional, há vários métodos, mas para diferenciá-los entre suas diferentes versões, aí já é mais difícil. Por isso essa parte já é bem **menos precisa**.



### Formato de Output

Possui 3 formatos:

- Normal: `-oN <path/output-file.txt>`
- Grepable: `-oG <path/output-file.txt>`
- Xml: `-oX <path/output-file.txt>`
- Script: `-oS <path/output-file.txt>`

Para imprimir todos de uma vez, use `-oA`

## Nmap Scripting Engine (NSE)
O NSE representa o poder de extensibilidade do nmap. Ao instalar o nmap, muitos desses scripts vem junto para adicionar em muito as funcionalidades e capacidades do nmap.

Os scripts costumam estar em `/usr/share/nmap/` scripts e são escritos em Lua, uma linguagem brasileira bastante usada e simples.

Os scripts são separados em categorias. Entre elas, estão:
- *vuln*: scripts de vulnerabilidade
- *safe*: scripts que não vão afetar o alvo.
- *intrusive*: scripts para abordagens não seguros e barulhentas.
- *auth*: scripts de invasão de serviços.
- *exploit*: scripts que tentam explorar um exploit.
- *discovery*: scripts de reconhecimento. Bem comum reconhecerem através da lista de serviços executados no alvo atualmente.
- *brute*: script de força bruta em credenciais.
- *default*: 
- *broadcast*: 
- *dos*: 
- *fuzzer*: 
- *malware*:
- *version*:

Mais detalhes em https://nmap.org/book/nse-usage.html.


Para ativar um script específico no scan, use a opção `--scripts=<script>`, enquanto que para ativar todos os scripts em uma pasta, use `--scripts <categoria>` ou `--scripts=<categoria>` ou ainda `--scripts <categoria>-*`

Scripts aceitam argumentos através da bandeira `--script-args <script>.<arg>`.

Caso queira saber mais sobre quais são todos os scripts pré instalados do nmap, você pode usar:
- Usar o arquivo `/usr/share/nmap/scripts/script.db`. Ele conté uma lista dos nomes dos scripts contidos no nmap local, assim como suas categorias. Apesar da extensão `.db`, ele é só um arquivo de texto.
- `nmap --script-help <script>` para mais detalhes sobre um script específico.
- Pode olhar a [documentação](https://nmap.org/nsedoc/).

Caso queira um script que não está na sua máquina, você pode:
- Procurar por ele no site do nmap, lá há todos os scripts oficiais para download.
- Fazer o seu próprio script em Lua.

Ao adicionar um script na pasta de scripts do nmap, lembre-se sempre de atualizar o `/usr/share/nmap/scripts/script.db` através do comando `nmap --script-updatedb`.

## Evasão de Firewall










