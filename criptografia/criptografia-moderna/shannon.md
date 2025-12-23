# Introdução à Criptografia Moderna - Teoria da Confidencialidade de Shannon

## Vernam e a ideia de *Perfect Secrecy*

Por volta dos anos 70, Shannon provou matematicamente o porquê a Cifra de Vernam era matematicamente o ***segredo perfeito***. A ideia consiste em criar uma forma de esconder a mensagem **que não revele pista ou indício algum de como resolver o esconderijo**.

Na prática, isso é alcançado na Cifra de Vernam com o uso de:
- *Chaves de mesmo comprimento da mensagem*: cada caractere tem um deslocamento independente.
- *Chaves de geração aleatória*: cada caractere criptografado não gera pista sobre o seu valor original.
- *Chaves de uso único*: nenhuma tentativa gera qualquer correlação com alguma tentiva futura ou anterior.

Interferir com qualquer um desses princípios na Cifra de Vernam o torna insegura. Nesse ponto, nem o tamanho da mensagem é relevante.

Entretanto, ainda que teoricamente ideal, criar chaves de tamanho não fixo e conteúdo completamente aleatório sempre é uma tarefa difícil e geralmente impraticável.

Baseado na análise de canais, podemos dizer que a Cifra de Vernam, ainda que um exemplo prático já existente na época de Shannon, tinha como características:
- **Alto custo computacional**. Justificava: era necessário no mínimo 2 vezes o tamanho da mensagem.
- **Baixa velocidade**. Justificativa: conseguir uma verdadeira aleatoriedade de valores é um processo lento e demorado.
- 
- **Segurança alta**.


## Modelo de Sistema Criptográfico de Shannon

Shannon formalizou o modelo criptográfico através de seus artigos e ideias sobre *perfect secrecy*. Em seu modelo:

1. Fulano quer enviar uma mensagem para Cicrano.
2. **Um sistema externo envia uma chave criptográfica por canal seguro a ambos.**
3. Fulano utiliza um Encriptador C(o, k), que utiliza como parâmetros o texto original(o) e a chave compartilhada(k). A chave é relevante na encriptação, alterando o resultado com base em seu valor.
4. O texto cifrado é enviado a Cicrano.
5. Cicrano utiliza o Decriptador D(c, k), que pede como parâmetros o texto encriptado(c) e a chave compartilhada(k) para então decifrar a mensagem.
6. Cicrano consegue ler o texto original.

![Sistema criptográfico de Shannon](assets/shannon-criptosystem-model)

Esse modelo já estava em vigor em alguns sistemas militares na época e seria mais tarde fixado como o modelo da **criptografia simétrica**, muito utilizada nos dias de hoje e essencial para o funcionamento da maioria, se não de todos os sistemas criptográficos.

Perceba que o modelo acima também possui 2 canais, o **canal da chave** secreta e o **canal da mensagem**. O modelo de Shannon nos permite fazer com que somente o canal de transmissão da chave necessite de segurança, já que **o canal da mensagem não indica nenhuma pista sobre o valor da chave secreta**. Separando assim o problema, agora podemos focar em aumentar os outros indicadores do canal de transmissão da mensagem, enquanto o canal da chave, que de fato precisa de segurança, não precisa de tanto investimento nos outros indicadores.

- Por que o canal da mensagem não precisa melhorar os outros indicadores?

Chaves costumam ter um tamanho menor do que a mensagem. **É muito mais fácil proteger um pequeno canal do que um grande canal**. Perceba também que a Cifra de Vernam possui o tamanho de chave igual ao da mensagem, já não se enquadrando tão bem nessa ideia do modelo.



## Entropia

Shannon emprestou da teoria da informação muitos conceitos em seus artigos, como a palavra *bit*, que significava uma "batida, escolha" na de Probabilidade. A partir do bit, que hoje é adotado amplamente na teoria da computação, Shannon pensou na **entropia**, essencial na criptoanálise.

Pensando em probabilidade, a entropia é definida como a média de incerteza de uma escolha. Em termos simples, a entropia é máxima quando for mais difícil de adivinhar qual o resultado de uma escolha ou série de escolhas.

Por exemplo:

*Se alguém bate na sua campainha, temos 4% de chance de ser um ladrão, 16% de chance de ser a sua encomenda internacional e 80% de chance de ser alguém vindo te cobrar o aluguel. Com quantas perguntas de "sim ou não" consigo decobrir quem é?*

Pensemos que as perguntas seriam estas:

A média de perguntas seria:

```
*Perguntas = probabilidade(Ladrão) * quantas_perguntas(Ladrão) + probabilidade(Amigo) * quantas_perguntas(Amigo) + probabilidade(Cobrador) * quantas_perguntas(Cobrador)*
```

OU

```python
perfis = [ladrao, amigo, cobrador]
resultado = 0
for perfil in perfis:
    resultado += probabilidade(perfil) * quantas_perguntas(perfil)
```

Por empirismo, a entropia de qualquer série de escolhas pode ser representada por uma concavidade para baixo, **com o pico de entropia sendo quando as chances para cada escolha são as mesmas**.