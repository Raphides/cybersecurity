# Autenticação

Autenticação é o processo que um sistema usa para provar que você é quem diz ser. Em um sistema, usuários normalmente proveem de identificações (usernames, IDs) aos quais afirmam ser e uma prova/fator de sua identidade. Os mecanismos de autenticação não só determinam que tipo de dados seriam as provas que os usuários precisam providenciar às suas contas, como também verificam se a prova oferecida por um usuário de fato é a que prova sua entrada ao sistema ou seção do sistema.

## Os 3 Fatores de Autenticação Comuns
É possível autenticar um usuário através de 3 fatores mais comuns. Fatores são vias de autenticação, o que se usa para autenticar-se.

### Algo que sabemos
Senhas, PINs, chaves de recuperação.


### Algo que temos
Possuímos outros dispositivos, aplicativos e outras contas em outros sites. Podemos normalmente provar a posse de algo que temos através de duas estreatégias:

- One Time Password (OTP): o dispositivo cria uma senha, código ou token que só pode ser usado uma única vez. O sistema autenticador tem como conferir se o código está correto e portanto autentica ou não o usuário. É ainda mais comum a utilização de Time-Syncronized One Time Password (TOTP), que são OTPs válidas somente por um curto período de tempo. É caso de Hardware Tokens, códigos de recuperação via email e SMS e apps autenticadores, como Microsoft Authenticator, Authy, etc.
- Plug-in: o dispositivo pode ser conectado ao sistema autenticador para demonstrar sua autenticidade. É o caso de cartões de acesso, pendrive-chave, etc. 

### Algo que somos

Assinatura biométrica dos dedos, scan de olho, etc.

## Outros Fatores de Autenticação
Menos comuns e às vezes até teóricos.

### Algum lugar em que está
Autenticação baseada em endereço de IP ou geolocalização.

### Alguém que você conhece
Autenticações baseadas num convite ou voucher de algum outro usuário.

### Algo que você faz
Assinatura, padrões de comportamento, linguagem, gírias, etc.

### Algo que você exibe
Personalidade, característica psicológica, padrão físico, etc.

## Multiple Factor Authentication (MFA)

O mais comum até alguns anos atrás eram autenticações utilizando somente um fator de autenticação. Atualmente há uma tendência de utilizar sistemas de autenticação que pedem uma autenticação via múltiplos fatores. O mais comum é a exigência de 2 fatores (2FA) e normalmente utiliza-se "Algo que temos" como o segundo fator.