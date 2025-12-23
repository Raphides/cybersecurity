# Criptografia Antiga

A criptografia antiga talvez seja mais próxima do entendimento natural de *codificação*, mas é mais longe da realidade da criptografia moderna.

Boa parte dessa distância entre ambas as eras se dá pelo conceito de *segredo*, ou seja, o que de fato deve ser escondido. Na criptografia antiga, o *segredo* era o algorítmo utilizado para codificar e decodificar as mensagens. Há relatos do uso de codificação com o intuito de esconder mensagens desde séculos atrás e vários métodos comuns eram usados antigamente e ainda são usados até hoje, mas de forma aprimorada. Entre eles, estão:

- Transposição
- Substituição
- Chaves Secretas

## Cílata dos Espartanos

Uma cilata é um pano de couro que é amarrado em um cilindro. Os espartanos escreviam a mensagem no couro através do eixo do cilindro e enviavam somente o pano de couro como a mensagem. Quando outra pessoa fosse ler o texto, ele só conseguiria ver a mensagem de em uma linha completa caso usasse o cilindro do mesmo tamanho. Esse método de criptografia antiga é conhecido como **transposição** e consiste em mudar as letras de ordem. Caso tenha dificuldade de entender como essa citala funciona, pense em anagramas. O que os espartanos fizeram foi gerar anagramas de suas mensagens, fazendo com que um receptor com o tamanho certo do cilindo visse o anagrama certo, enquanto um receptor com o tamanho errado visse um anagrama errado e bagunçado da mensagem.

Perceba que se soubessem da diferença entre o uso dos cilindros, poderiam testar incansavelmente vários cilindros de dimensões distintas até que se chegasse a uma dimensão aceitável. Garanto-lhe que isso não seria difícil de fazer e portanto, quebrar a criptografia dos espartanos.

## Cifra de César

Muito famosa quando se fala em criptografia antiga, a Cifra de César era o método que a Roma Antiga usava para comunicar mensagens secretas através das grandes distâncias de seu vasto império. César usou o método de **substituição simples** em suas mensagens, substituindo as letras do alfabeto por outras (do mesmo alfabeto). Sendo o alfabeto deles composto por 21 letras, "a" a letra de 1ª posição (index 0) e "x" a de 21ª posição (index 20), cada letra ao ser cifrada era substituída pela letra 3 posições a sua frente. É importante notar que não era simplesmente uma soma de 3 posições no index da letra, era uma soma de 3 posições do módulo de 21, ou seja, caso a index + 3 passasse de 20, era considerado somente o resto de `index + 3 / 21`. Logo `abx` cifrado seria `DEC`.

Caso a cifra fosse descoberta na época, todas as mensagens de César estariam inseguras. E mesmo se César mudasse a quantidade de posições deslocadas, é possível quebrar a cifra com o método de **frequência de letras**, que busca calcular a probabilidade de uso de determinadas letras, sílabas, diagramas e trigramas em um sistema de código. A partir desse cálculo probabilístico, as opções de candidatos a texto puro diminuem bastante.

Atualmente a Cifra de César ainda é aplicada no ROT13 do sistema UNIX.


## Cifra de Vigenère (séc. XVI) e Cifra de Vernam

A Cifra de Vigenère é um aprimoramento da Cifra de César e na realidade, serve como um método que engloba tanto a Cifra de César quanto a Cifra de Vernam. A Cifra de Vigenère introduz o conceito de **chave secreta** como o *segredo*, mudando o paradigma até então usado pelas cifras anteriores e dando um passo em direção à criptografia moderna.

Tanto a Cifra de Vigenère, quanto a de Vernam e quanto os demais métodos da criptografia moderna funcionam usando a chave secreta como o único segredo do sistema, fazendo com que a descoberta dos algorítmos não significasse o imediato fim da solução. Isso não faz com que todos os algorítmos de criptografia aí em diante sejam públicos, mas seus sistemas foram desenvolvidos para manter seu aspecto seguro mesmo no caso do vazamento.

A Cifra de Vigenère usa como base o método de substituição usado na Cifra de César, o de substituição alfabética modular (substituição do alfabeto através do aritmética modular de suas posições), mas saindo das rédeas da substituição simples. Mas ao invés de sempre substituir a letra pela sua correspondente x posições à frente, ele usaria uma **chave secreta K**, uma palavra com tamanho menor ou igual a mensagem encriptada. Essa chave teria as posições somadas com as posições das letras da mensagem. Caso K tivesse um tamanho menor que a mensagem, as letras de K recomeçariam:

```txt
Alfabeto de 26 letras.
Texto Puro: criptografia.
Chave: ABC

c + A = C
r + B = S
i + C = K
p + A = P
t + B = U
o + C = Q
g + A = P
r + B = S
a + C = C
f + A = P
i + B = J
a + C = C

Texto encriptado: CSKPUQPSCPJC
```

Caso o segredo fosse descoberto, ou seja, a chave, era muito mais fácil mudar a chave do que o sistema criptográfico. Isso vale principalmente para os sistemas eletrônicos de hoje.

Quando o tamanho da chave for 1, a Cifra de Vigenère vira novamente uma substituição simples, ou seja, a Cifra de César. Já quando o tamanho da chave é igual ao tamanho da mensagem, damos um passo em direção a Cifra de Vernam.

---

A Cifra de Vernam é basicamente isso:
- Uma cifra de Vigenère com uma chave do tamanho (n) da mensagem.
- Vernam trabalha com números binários. Mensagem e chave de {0,1}^n
- Sua cifra é simples: uma operação XOR entre o texto puro e a chave.
- Cada chave só pode ser usada uma única vez.
- A complexidade se dá a partir da geração de chaves aleatórias. Chaves pseudo-aleatórias apresentarão vulnerabilidades ao sistema.
- A segurança da cifra se dá a partir da aleatoriedade e unicidade das chaves.

Infelizmente os requisitos de criação da chave são um grande problema e a violação dessas regras da cifra com o reuso de algumas chaves pela KGB em seu sistema criptográfico (que utilizava a Cifra de Vernam) nos anos 40 resultou na quebra da criptografia pela NSA e o famoso projeto VERONA.


---

Os métodos e conceitos aqui da criptografia antiga utilizados no sistema ENIGMA na Segunda Guerra Mundial seria a causa para a criação dos computadores por Alan Turing e posteriormente a motivação da criação da criptografia moderna.