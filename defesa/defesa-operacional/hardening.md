# Hardening

Hardening é a aplicação de políticas e configurações nos sistemas que os deixem mais seguros. É um conceito muito importante para qualquer sistema, principalmente servidores que planejem ser expostos a ambientes externos.

É importante entender que cada hardware e software possui uma forma distinta de ter sua segurança fortificada através de *hardening*. Por isso que nessas anotações, o assunto hardening não será muito especificado, porque depende muito do servidor que você está montando e quais aplicações ele terá. Entretanto, serão mostrados alguns exemplos comuns de servidores que devem ser fortificados, um panorama geral de como configurar esses casos e onde achar guais completos de hardening do seu servidor.

---

Caso não saiba, servidores são computadores com o objetivo de servirem aplicações e serviços. Eles normalmente atuam via rede e processam dados e requisições, entregando resultados também em formato de dados. É muito comum ouvir falar de servidores web. Servidores web normalmente servem várias aplicações web e tem uma parte de sua capacidade oferecida por provedores a desenvolvedores a fim de hospedarem os seus serviços na máquina. Dessa forma, servidores estão presentes no dia a dia de qualquer usuário da internet, mas por debaixo dos panos (backend).

Servidores podem oferecer diferentes categorias de serviços. Entre essas categorias, podemos citar:
- Servidor DNS: servidores que junto ao protocolo DNS, são responsáveis por oferecer todos os serviços de tradução de IPs para nomes de domínio e vice-versa na rede.
- Servidor DHCP: servidores que junto ao protocolo DHCP, são responsáveis por oferecer todos os serviços de distribuição de IPs.
- Servidor Web: servidores que hospedam aplicações web e portanto são responsáveis por receber e responder a requisições HTTP e derivados. São muito comuns servidores web da:
    - Apache
    - NGINX
    - TomCat


## Servidor Windows

É extremamente comum utilizar os sistemas operacionais *Windows Server* para programar e construir servidores operacionais completos para hospedar aplicações. Normalmente os servidores Windows Server mais atuais tem a fama de se assemelharem muito aos Windows Desktop e portanto são fáceis de manusear e configurar através da interface gráfica. Servidores Windows mais antigos entretanto eram mais conhecidos por suas interfaces de linha de comando.

Os servidores Windows já perguntam os serviços que você pretende incluir no servidor durante as primeiras instalações e configurações.


Não há muita dificuldade em configurar servidores Windows de interface gráfica, entretanto **há muitas opções** e é mais fácil e seguro seguir os padrões de segurança recomendados por órgãos de segurança. É recomendada as configurações do ...


## Servidor Linux

Os servidores Linux já não são tão simples quanto os servidores Windows. Primeiramente já devemos começar lembrando que em sistemas Linux prevalecem interfaces de comando e para servidores Linux não é diferente. Segundo: existem várias distribuições e versões do linux competentes para servirem como servidores e cada uma possui uma série de configurações diferentes a serem exploradas. É necessária uma expertize e paciência maior nesse módulo.

É mais comum o uso dos Ubuntu Server e do Debian Server mais recentes, mas ainda há outras distros que são muito utilizadas. Além disso, para os serviços oferecidos no linux, é recomendado:
- Servidor DHCP:
- Servidor DNS: *bind9*
- Servidor Web: apache, ngnix, tomcat.