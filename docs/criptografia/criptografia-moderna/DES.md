# Data Encryption Standard (DES 1977 - 2004)

Oficializado em 1977, o DES foi um dos primeiros padrões de criptografia moderna adotados. Hoje em dia, ele é datado e não é mais recomendado pela NIST desde 2004, mas mesmo assim ainda é amplamente utilizado no sistemas atuais, assim como suas variações e derivações.

O DES é muito bem descrito através de suas características gerais:
- Criptografia Simétrica.
- Baseada em blocos: criptografa blocos de mensagens de 64 bits.
- Mais voltada a implementação em hardware.

Na década de 70, com a teoria de Shannon já conhecida, o DES tenta implementar um **sistema de criptografia simétrica** seguro, mas que seja de implementação viável, diferente da cifra de Vernam. O que torna a cifra de Vernam segura é ao mesmo tempo o que a torna inviável na prática e portanto, ao criar um sistema criptográfico viável para a época, já era de se esperar que ele não seria de fato seguro. Mas talvez fosse possível adicionar mecanismos que tornassem a decifragem mais difícil de ser realizada e é isso que o DES tenta alcançar.

O mundo de tecnologia nos anos 70 era mais voltado para hardware e o DES não é diferente. Em sua implementação, vemos fios e portas lógicas sendo utilizadas. Sem contar o seu modelo baseado em blocos, criptografando um bloco de 64 bits por vez. Isso se relaciona muito com o mundo de hardware, visto que costuma apresentar inputs e outputs de tamanhos fixos em bits. Essa característica é contrastrante com sistemas criptográficos mais modernos que costumam se aproximar mais do mundo matemático ao utilizar hashes, algorítmos que aceitam inputs de qualquer tamanho.



Quando estudamos DES, é imprescindível ver os seguintes componentes que ele possui:
- A Base do DES - Esquema Feistel.
- Permutação de *Funções Redondas*.
- Chave Secreta e Agendador de Chaves.

### Feistel Scheme
A cifra usada no DES foi criada por Feistal e é baseada em sua cifra anterior, o LUCIFER. O DES utiliza o *Feistel Scheme*, um fluxo de circuito.

### Permutação de Funções Redondas no DES

#### Fase 1: de 4 a 6 bits

#### Fase 2: circuitos de substituição.
Os circuitos de substituição não nada extremamente complexo. Eles simplesmente "criptografam" os inputs substituindo os valores recebidos de acordo com uma tabela de substituição. Com essa mesma tabela, também é possível "descriptografar". Veremos isso a seguir.

![Tabela de substituição do DES]()

- Criptografar:

- Descriptografar:

#### Fase 3: transposição por cabos.
Pega os outputs da fase anterior e troca a ordem dos resultados através de uma transposição de fios. Como é uma implementação em hardware, uma transposição de cabos gera bastante confusão. Para "criptografar" a mensagem resultado da fase 2, é só seguir os cabos na direção esperada. Para voltar à mensagem não-transposta, é só seguir a direção contrária dos cabos.

### Chave Secreta e *Key Scheduler*
Baseado na Cifra de Vernam, o DES utiliza chaves de 64 bits por bloco. Entretanto, saindo um pouco da Teoria do "Segredo Perfeito" de Shannon, somente 56 bits da chave são de fato efetivos, gerando chaves reais de tamanho distinto do bloco de 64 bits.

Uma chave por bloco? Mas e as diversas chaves utilizadas no esquema de Feistel a cada bloco? Elas todas são uma **variação da chave original** de 56 bits adquirida por bloco. Essas variações são geradas a cada ciclo do esquema de Feistel através do **Programador/Agendador de Chaves**.

O Programador de chaves funciona de acordo com a seguinte lógica de programação:

```c
a preencher
```

## Modos de Operação para o DES para mensagens maiores que 64 bits.

###
###
###
###

###
###

## Aplicação real e atual do DES: Senhas do sistema Unix

Caso não conheça o sistema Unix, ele cuida de suas credenciais internas através dos aplicativos `/etc/shadow` e `/etc/passwd`. Nesta última, podemos ver uma série de textos cifrados