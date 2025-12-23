# Conceitos Introdutórios

Antes de qualquer ensino sobre a criptografia, é preciso entender alguns conceitos básicos do processo, assim como um fluxo e objetivo gerais desse campo.


## Princípios da Criptografia
O objetivo da criptografia permea 3 valores, a pirâmide CIA (en-us) / CID (pt-br):
- Confidencialidade: se uma informação só é de fato acessada por quem é permitida acessá-la.
- Integridade: se é possível afirmar que uma informação continua a mesma desde sua partida até seu destino. O contrário do telefone sem-fio.
- Disponibilidade: se uma informação está sempre disponível quando é prevista que ela esteja.

Mais tarde, durante a implantação da criptografia moderna, mais princípios foram adicionados como da alçada dos sistemas criptográficos:

- Não repudiação: sempre poder provar a origem de uma mensagem ou documento.

Esses objetivos são algumas das características que diferencia codificação de criptografia.

### Codificação:

Toda linguagem possui um código pré estabelecido. As linguas faladas por exemplo possuem como código a **gramática**, que estabele como seus caracteres, chamados de letras, devem ser organizados. Linguagens de programação por sua vez possuem uma documentação que especificam os códigos que lhes definem. O campo de codificação trabalha com o estudo, uso e transformação entre os diferentes códigos presentes em nossa história. Uma tradução de um programa da linguagem C para um código binário está na área da codificação, mas dificilmente se configura como criptografia, justamente por **não ter como norte esses princípios de segurança**, a confidencialidade, integridade e disponibilidade. Um sistema de codificação não será chamado de sistema criptográfico quando o mesmo tiver sua insegurança provada. Mais detalhes sobre o nível de segurança de um sistema de criptografia será abordado em breve.

Entretanto, é importante notar que a criptografia se utiliza da codificação e portanto alguns elementos da *teoria da codificação* será importante na criptografia.

---

O fluxo simples da criptografia é o seguinte:

1. Fulano tem uma mensagem em *texto puro (plaintext)* e quer enviá-la a cicrano.
2. Fulano *cifra* a mensagem em texto puro para *texto cifrado (cyphertext)* ao utilizar algum *encriptador*.
3. A mensagem viaja através do *canal de comunicação*.
4. A mensagem é *decifrada* por Cicrano ao usar um *descriptador*, recuperando a mensagem original em texto puro.
5. Cicrano lê a mensagem em texto puro.

Esse fluxo acaba se tornando mais robusto e detalhado conforme o crescimento da criptografia na história. Mas perceba que já agora o fluxo anterior apresenta vários termos um tanto específicos e que serão muito importantes no estudo da criptografia:

- Texto puro (plaintext): mensagem original de um comunicador.
- Codificar: traduzir uma mensagem passada num código para outro código. Decodificar seria traduzir esse resultado para o código original.
- Cifra: a ação de cifrar / encriptar, ou seja, codificar um texto puro em um código seguro (de acordo com os princípios anteriores); o método de encriptação.
- Texto cifrado (cyphertext): mensagem cifrada em um código seguro.
- Decifrar: transformar um texto cifrado em um texto puro, decodificar um texto cifrado.

## Canal de Comunicação:
Um canal de comunicação são os meios pelos quais a comunicação entre diferentes atores pode ser realizada. Canais de comunicação podem ser avaliados conforme os seguintes índices:
- Custo (associados a manutenção do canal)
- Velocidade (de transmissão)
- Disponibilidade (de uso)
- Confiabilidade (contra ruídos na comunicação, campo da teoria dos códigos)
- **Segurança**

O desafio é criar um canal que equilibre todos os índices. Uma conversa física entre amigos é veloz e confiável, mas pode custar caro quando o amigo mora longe, assim como pode não ser tão seguro caso algum bisbilhoteiro ao lado esteja ouvindo. Um canal com o algorítmo criptográfico mais robusto e seguro da nossa época com toda certeza seria seguro, mas a velocidade tenderia a ser extremamente lenta, a disponibilidade muito provavelmente seria baixa e o custo com certeza seria altíssimo. Assim criptografia não é só sobre os seus conceitos centrais de segurança, como também sobre as consequências de sua implementação num negócio.
