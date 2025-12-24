# Introdução a criptografia

Primeiro será abordado onde a criptografia se encaixa no manuseio de dados e o que criptografia não é. Depois será abordado mais especificamente o que é criptografia e um pouco sobre seus algorítmos. E por fim, será abordado como a criptografia é aplicada no mundo.

## Mascaramentos de dados

Mascaramento de dados é uma prática que visa modificar dados sensíveis com o intuito de escondê-los, mas ainda mantendo esse dado utilizável. Deve ser utilizável o bastante para máquinas legítimas e estudiosos, mas não muito utilizável para atores maliciosos. Geralmente o mascaramento de dados cai muito como uma anonimização dos dados e intermediação (uso de proxy e NAT).

Criptografia é um meio de mascaramento e ofuscação de dados. Como máscara, a criptografia nem sempre é a melhor opção, já que nem todos os algorítmos tentam manter o formato do texto criptografado. Por exemplo: ao retornar uma tupla de um banco de dados com cpf e nome, o mascaramento causado por alguns algorítmos criptográficos poderia não ser tão útil.

(Mpleg3oeFWPrd6hjAjhgyOj8648gyhWM9m0uj-gyF, Raphael Mendes da Silva)

Talvez uma abordagem desse tipo seja mais interessante para mascaramento e anonimzação:

(000.000.000-00, Raphael Mendes da Silva)

Algumas técnicas de mascaramento de dados são:
- Substituição
- Embaralhamento
- Anulação e *Masking Out*
- Tokenização
- Criptografia

Tipos de mascaramento de dados:
- Máscara de dados estáticos (*at rest*)
- Máscara de dados dinâmicos (*in transit*)

## Esteganografia

Não é criptografia, mas é muitas vezes confundida e mencionada junto à criptografia.

Esteganografia é a arte de esconder a existência de mensagens, enquanto criptograifa é a arte de esconder seu significado.

Uma téncica comum de esteganografia é esconder uma mensagem dentro da outra. Textos escondidos dentro de textos, pixels escondidos em imagens que podem ser traduzidos para um texto, ambos representam esteganografia.

Na questão de segurança cibernética, há vários programas que podem esconder um arquivo em outro. Fotos com executáveis malciosos dentro dele são um exemplo clássico. É comum que esses executáveis internos sejam criptografados também para ajudar ainda mais a ofuscação.

Arquivos que ocupam um espaço maior do que deveriam ter é um sinal provável de esteganografia.

## Tokenização

Tokens é qualquer coisa que substitua dados sensíveis com dados não sensíveis.

Há dois tipos de tokens:
- Tokens de Alto Valor
- Tokens de Baixo Valor

## Hashing
Não é criptografia, mas é normalmente mencionado junto a criptografia. Um algorítmo hash se refere a uma função matemática que tenta gerar valores únicos (hashes) de resultado a partir de um argumento de entrada. Funções hashes devem enforçar a propriedade de distanciamento, ou seja, qualquer mudança pequena ou grande no argumento deve gerar um hash completamente diferente de resultado.

Os algorítmos de hashing atuais aceitam que os argumentos de hashes podem ser de tamanhos variados, enquanto os hashes em si (resultados) são de tamanhos fixos. Dessa forma, não importa qual algorítmo, haverá **colisões** de argumentos diferentes gerando hashes iguais.

Hashes são usados para testes de integridade, sistemas de autenticação e assinaturas digitais. Por exemplo, ao salvarmos uma senha no nosso sistema Linux, não é a senha que é salva, mas sim o seu hash, impedindo que um hacker descubra a senha a partir do hash. Ao logar no sistema, a senha oferecida pelo usuário passa pelo algorítmo de hash e é comparada com o hash armazenado no sistema. Se verdadeiro, a senha está correta.

Alguns algorítmos hashes de exemplo:
- MD5
- SHA1
- SHA2

---
Agora que vimos principalmente o que não é criptografia, podemos nos aprofundar no que é criptografia.

Já vimos que a criptografia é um mascaramento de dados com o intuito de esconder o significado de uma mensagem de usuários indesejados. Ela precisa ter seu resultado (texto encriptado) reversível ao texto original e esse processo de reversão deve ser feito com facilidade pelo destinatário, a fim de estabelecer um comunicação segura em um canal de comunicação inseguro. 

O que transforma um texto pleno em um texto encriptado e vice-versa é chamado de algorítmo criptográfico. Existem vários algorítmos criptográficos, mas em geral, eles se dividem em duas categorias:

## Criptografia Simétrica

Criptografia moderna que utiliza uma única chave para encriptar e desencriptar mensagens a partir de funções matemáticas. Essa chave é compartilhada com os usuários que participam da comunicação.

O desafio matemático aqui é criar funções em que:

- encriptar(mensagem_original, chave) == mensagem_encriptada
- desencriptar(mensagem_encriptada, chave) == mensagem_original

Quando um atacante descobrir a chave, ele pode entender e participar de toda conversa. E como a chave é a mesma compartilhada pelos participantes da comunicação, basta um computador vulnerável para comprometer toda a segurança de armazenamento da chave.

Em contrapartida, criptografia simétrica é mais rápida do que a assimétrica.

Exemplos de algorítimo de criptografia simétrica:
- DES

## Criptografia Assimétrica
Criptografia mais moderna, composta por dois tipos de chave: chave pública e chave privada.

A chave pública é responsável na maior parte dos sistemas por encriptar dados. Ela é chamada de pública porque é prevista para ser exposta ao público.

Já a chave privada é usada principalmente para desencriptar dados. Ela é chamada de privada porque não deve ser compartilhada.

O desafio matemático aqui é criar uma função em que:

- chave_publica != chave_privada
- encriptar(mensagem_original, chave_publica) == mensagem_encriptada
- desencriptar(mensagem_encriptada, chave_privada) == mensagem_original

Na comunicação entre dois indivíduos, cada um tem seu par de chaves privada e pública. A chave pública de cada um é compartilhada, enquanto as chaves privadas são guardadas. Dado os indivíduos A e B, quando A quer enviar mensagens para B, ele as encripta através da chave pública de B e as envia ao B. B as desencripta com a sua própria chave privada. Em seguida, ele manda uma mensagem para B, mas antes a encripta usando a chave pública de A. A recebe a mensagem encriptada e a desencripta com sua própria chave privada.

Se a chave privada de alguém vazar para atacantes, eles serão capazes de ler as mensagens enviadas àquela pessoa, o que é uma violação de confidencialidade. É necessário proteger a transmissão e armazenamento da chave privada.

Há casos em que se encripta com a chave privada e desencripta com a pública, como forma de não repudiação. Um exemplo é na **assinatura digital**. Como a chave privada é pessoal e não compartilhada, se a chave pública desencriptar a mensagem, então com certeza ela foi encriptada pela chave privada e com certeza o sistema a encripta-la é o sistema que deveria encripta-la.

<!--Em muitos algorítmos de criptografia, é possível deduzir a chave pública a partir da chave primária, então proteger o armazenamento da chave privada é ainda mais importante.-->

Exemplos de algorítmos assimétricos:
- RSA
- 


O resto dos tópicos dessa seção abordarão assuntos tangentes ao funcionamento da criptografia, como suas aplicações, conceitos semelhantes, tópicos que acompanham o tema, etc. Eles normalmente são comentados junto a criptografia e podem lhes ajudar a entender o que criptografia é e não é e como ela está inserida no mundo. Alguns desses tópicos podem ser aprofundados mais para frente durante esse capítulo.

-----
Em seguida, conta-se um pouco sobre como criptografia está aplicada no mundo e quais assuntos tangem os algorítmos criptográficos.

## Transmissão de Chaves
Tanto na criptografia simétrica, quanto na criptogragia assimétrica, os sistemas se esforçam mais na segurança do canal e da transmissão da chave. O benefício é não ter que se esforçar tanto para proteger a transmissão de mensagens, já que o algorítmo ciptográfico e as chaves transmitidas já o fazem. Isso gera um custo menor do que tentar proteger ao máximo toda transmissão contra invasões, leituras e modificações de outras formas.

### Out of Band Key Exchange
A chave é transmitida fora da rede. É necessário utilizar outros métodos, como cartas, ligações ou até mesmo comunicar a chave pessoalmente.

### In-Band Key Exchange
A chave é transmitida através da rede. Há de se tomar um cuidado. Por exemplo, na web, as chaves costumam ser criadas no início de uma sessão e descartadas no fim dessa sessão.

## Public Key Infrastructure (PKI)

É uma infraestrutura de componentes que permitem o uso de certificados digitais e criptografia assimétrica (chave pública e privada). Aqui infraestrutura é composta por hardware, software, pessoas, políticas e procedimentos.

Os procedimentos de criptografia simétrica e assimétrica já fazem parte da PKI.

### Política: Escrow de Chave

Acordo entre dois ou mais agentes para que um agente/órgão/empresa armazene as chaves criptográficas de decriptação dos sistemas dos outros agentes. Normalmente é um acordo feito com recuperação em mente.

Entre as desvantagens, está a possibilidade do agente que guarda as chaves não ser segura o suficiente e todas as chaves vazarem.

### Armazenamento Seguro: Trusted Plataform Module (TPM)

Área segura normalmente integrada num dispositivo para armazenar chaves criptográficas. O termo TPM pode se referir tanto ao hardware (chip TPM) quanto a especificação utilizada para construir esse chip. Chips TPM costumam ser integrados à placa mãe do computador.

### Armazenamento Seguro: Haardware Security Module (HSM)

Dispositivos removíveis com o propósito de armazenar de forma segura chaves criptográficas. Diferente do TPM, os HSMs não precisam estar integrados ao sistema desde a sua fabricação e podem ser instalados depois.

Podem ter vários formatos, desde cartões até dispositivos maiores.

### Armazenamento Seguro: Secure Enclave

Subsistema dedicado de segurança. Está integrado aos chips de sistemas da Apple, como Iphones, Ipads, Macs, etc. Ele é isolado do processador principal para prover uma camada extra de segurança.

### Armazenamento Seguro: Sistema de Gerenciamento de Chaves

Plataforma interna ou externa (terceiros) de uma empresa usada para gerenciar as chaves utilizadas para encriptar e desencriptar outros sistemas da empresa. Apesar de interessate, também é perigoso, já que um vazamento desse gerenciador significaria a perda de segurança criptográfica de todos os sistemas encriptados daquela empresa.


## Assinatura Digital

Assinatura digital é um método que aplica integridade e não repudiação a qualquer transferência de dados. Ela utiliza conceitos de hash e criptografia assimétrica em seu funcionamento.

### Funcionamento geral:

Relembrando a [aplicação clássica de transferência de arquivos do hash](./hash.md#Aplicações), o remetente extrai o hash antes de enviar o arquivo. Depois ele envia o arquivo ao destinatário e o hash num canal que garanta mais integridade. O destinatário extrai o hash do arquivo recebido e compara o hash resultante com o hash enviado. Se ambos forem iguais, o arquivo foi enviado sem mudanças de bits e a integridade é garantida.

De forma semelhante, o remetente, ao invés de enviar o hash, ele o encripta com a sua própria chave privada. O arquivo tem anexado esse hash encriptado e portanto recebe o nome de "documento assinalado". O documento assinalado é enviado ao destinatário, que desencripta o hash encriptado com a chave pública do remetente. Por fim, o destinatário extrai o hash do arquivo enviado e compara com o hash desencriptado.

O que é encriptado com a chave privada do remetente só pode ser desencriptado pela chave pública do remetente e portanto serve como um atestado de não repudiação.

![Assinatura Digital](../assets/assinatura_digital.png)

### Certificado Digital
Enquanto o hash encriptado pela chave privada serve como alguma verificação de identidade, um certificado digital também é anexado ao documento assinalado antes de ser enviado.

Ao menos no Brasil, assinaturas digitais com valor jurídico e legal necessitam de um **certificado digital**, pois faz parte de provar a identidade de quem está assinando os dados. Esses certificados devem ser emitidos por **Autoridades Certificadoras (ACs ou CAs em inglês)**.

No Brasil, essas ACs precisam ser reconhecidas pela ICP-Brasil (Infraestrutura de Chaves Públicas Brasileira).

Autoridades Certificadoras comuns são Symentic, GeoTrust, DigiCert, GlobalSig, Comodo, Entrust, Thawte, etc.


### CSR - Certificate Signing Request
Processo de requisição de um certificado digital a uma AC. É exigida uma série de informações, normalmente seguindo a PKCS #10 (*Public Key Cryptography Standards*)