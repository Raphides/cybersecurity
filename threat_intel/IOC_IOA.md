# Indice of Compromise and Attack

## Indice of Compromise (IoC)

Os indicadores de comprometimento são trechos de informação que se encontrados relacionados a um sistema, podem indicar o seu comprometimento. Exemplos seriam endereços URL maliciosos aos quais um malware se conecta.

Atuais problemas com indicadores de comprometimento são:
- Grandes volumes de IoCs todo dia.
- IoCs podem ser extremamente dinâmicos e flutuantes.

### Características de IoCs conhecidos:

Os tipos de IoCs recebidos são vários e normalmente classificamos eles de aordo com o quão confiáveis são para um time de defesa utilizar em bloqueios de ataques.

![Pirâmide de Confiança]()

#### Hashes de artefatos

Artefatos são os produtos de software utilizados. Um hash identifica unicamente um artefato e portanto, no caso de um artefato malicioso, sempre irá impedir esse mesmo arquivo de penetrar. Logo ter como IoCs hashes de artefatos gera:

- Muita confiança, já que um hash identifica um malware num sistema sem erro, há não ser que o código do malware seja mudado.
    - Empacotadores podem mudar o hash de um arquivo e eles são bem comuns.

#### URL
Apesar de ser simples para ataques mais sofisticados mudarem sua URL, elas normalmente identificam uma URL pela


#### Domínio
- Confiável


#### IP + Porta
- Baixa confiança


#### Somente IP
- Pouco confiável, dificilmente identifica um ataque por si só.
- Se um atacante trocar sua placa de rede, ele realiza o mesmo ataque num IP diferente. O mesmo funciona ao usar a rede Tor.

#### CIDR
- Pouco confiável, dificilmente um CIDR identifica ou representa um ataque.


## Indice of Attack (IoA)
Refere-se aos comportamentos que o ataque demonstrou durante sua cadeia. É normalmente representado através de frameworks como Cyber Kill Chain e Mitre ATT&CK.

Comparado aos IoCs, IoAs são mais difíceis de um atacante mudar. Mais especificamente, um atacante muitas vezes precisa reformular toda a sua estratégia e ferramenta de ataque para gerar uma mudança em seu IoA. Toda essa discussão pode ser vista na **Pirâmide da Dor**, criada por David Blanco.

![Pirâmide da Dor]()

A *pirâmide da dor* mapea o que é fácil e difícil do atacante mudar comparado com a sua quantidade encontrada por times de Threat Intel. Mudar o hash que ele usa ou o seu endereço de IP é fácil, mas mudar seus comportamentos começa a ser mais difícil. Da mesma forma, achamos grande volume de hashes e IPs diferente em ataques, mas o comportamento típico do ataque tende a ser bem estável.

O topo da pirâmide se refere aos IoAs, ou TTPs:

- **Táticas**: os grandes objetivos por trás de cada sequência de ataquies.
- **Técnicas**: um detahamento de como as táticas foram atingidas. A estratégia por trás da tática.
- **Procedimentos**: detalhamento técnico para realizar a técnica e atingir o objetivo.
