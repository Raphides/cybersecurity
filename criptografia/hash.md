# "Funções" Hash

É uma "função" matemática que recebe um **input de tamanho indeterminado** e devolve um **identificador único** de **tamanho fixo** que **não pode ser revertido** ao input original. O diferencial dos algorítmos de hash é que duas informações similares com uma diferença mínima de um único bit **geram hashes completamente diferente um do outro**.

## Aplicações
Hash normalmente está relacionado com identificação e integridade.

- **Verificação de integridade na transferência de arquivos**: ao realizar o hashing de um arquivo antes e depois da transferência, caso os hashes resultantes continuem iguais, o arquivo também permanece o mesmo.
- **Armazenamento de senhas para futuras autenticações**: ao invés de armazenar a senha no sistema e dar chance ao atacante fazer uma forense e ler a senha armazenada, o Linux salva somente o hash das senhas no `/etc/shadow`. Dessa forma, quando um usuário inserir a senha para fazer login, o input dele entra no algorítimo de hash do sistema e o hash resultante é comparado com o hash da senha. Se forem iguais, o input inserido de fato era a senha.

## Característiscas:
- Input de tamanho e valor varíavel. Usa-se todo o conteúdo dos arquivos, byte a byte.
- Output de tamanho fixo, mas conteúdo extremamente variado a cada mudança, seja ela a mínima que for.
- Se H(in) = out é a função Hash, não há como conseguir *in* novamente através somente da informação *out*.

## Colisões

Algorítmos de hashing podem possuir colisões, ou seja, inputs diferentes que geram outputs iguais, o que tira o posto identificador único. Para evitar colisões, podemos escolher algorítmos que não possuem colisões conhecidas ou identificar um malware através de hashes gerados por algorítmos diferentes. A chance de ambos gerarem colisões no mesmo caso é extremamente baixa.

## Algorítmos de hashing:
- MD5 (possui coliões previsíveis)
- SHA1 (possui colisões previsíveis)
- SHA2:
    - SHA256
    - SHA384
    - SHA512

## Brute Force, Rainbow table, Salt e charound
***Brute Force*** (força bruta) é um ataque que usa de tentativas repetitivas, de input e output para achar correspondências ou padrões. Se um algorítimo de hash é muito pequeno, ele pode ser quebrado à força. Mas sendo um pouco maior, pode demorar séculos até quebrar.

**Ataques por *rainbow tables*** são uma alternativa ao brute force. A expressão *rainbow table* se refere a grandes bancos de dados que mapearam alguns padrões conhecidos e clássicos de output do algorítmo de hash para inputs comuns, ajudando por exemplo a quebrar senhas como "adminadmin" ou "12345".

A fim de contornar rainbow tables, usam-se ***salts*** no algorítmo de hash. Salts são uma sequência aleatória de texto ou baseada em algum outro fator difícil de replicar. O Salt é concatenado ao input do algorítmo de hash e por isso muda completamente o hash resultante.


```
Exemplo com hash no /etc/shadow do linux

fulano:$1$dawdgsad$sALDKA~DDAWLSfawfsahgkul:130422:0:99999:30:::


Estrutura (separado por ":"):

usuário :
$ algorítmo $ sal $ hash resultante :
ultima data de modificação :
mínimo de dias para liberar modificação de senha :
máximo de dias para liberar modificação de senha :
nº de dias antes da senha expirar para avisar da expiração:
nº de dias após senha expirada em que a conta será desabilitada:
data de expiração da conta):
```


***Charound*** também é outra técnica para evitar rainbow tables e brute force. Baseia-se em aplicar o hash múltiplas vezes ao invés de só uma vez, aumentando em muito a complexidade assintótica de adquirir os padrões comuns de rainbow table.




