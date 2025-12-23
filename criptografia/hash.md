# "Funções" Hash

É uma "função" matemática que recebe um input de tamanho indeterminado e devolve um identificador único de tamanho fixo e não pode ser reversível. O segredo dos hashes é que uma pequena alteração gera um hash completamente diferente um do outro.

Portanto Hashes trabalham com identificação e integridade.

## Aplicações
- Verificação de transferência de arquivos.

## Característiscas:
- Input de tamanho e valor varíavel. Usa-se todo o conteúdo dos arquivos, byte a byte.
- Output fixo e extremamente variado por mudança.
- Se H(in) = out é a função Hash, (1/H)(out) não é possível ser feito ou não gera o input

## Colisões

Algorítmos de hashing podem possuir colisões, ou seja, inputs diferentes que geram outputs iguais, o que tira o posto identificador único. Para evitar colisões, podemos escolher algorítmos que não possuem colisões conhecidas ou identificar um malware através de hashes gerados por algorítmos diferentes. A chance de ambos gerarem colisões no mesmo caso é extremamente baixa.

## Algorítmos de hashing:
- MD5 (possui coliões previsíveis)
- SHA1 (possui colisões previsíveis)
- SHA2:
    - SHA256
    - SHA384
    - SHA512

## Brute Force, Raimbow table, Salt e charound
***Brute Force*** (força bruta) é um ataque que usa de tentativas repetitivas, de input e output para achar correspondências ou padrões. Se um algorítimo de hash é muito pequeno, ele pode ser quebrado à força. Mas sendo um pouco maior, pode demorar séculos até quebrar.

Semelhante a força bruta, ***raimbow tables*** são grandes bancos de dados que mapearam alguns padrões conhecidos e clássico do hash, ajudando por exemplo a quebrar senhas comuns, como "adminadmin" ou "12345"

A fim de contornar raimbow tables, também usam-se ***salts*** no hash. Salts são uma sequência aleatória de texto ou baseada em algum outro fator difícil de replicar. O Salt entra no hash também e muda completamente o output do hash.


```
Exemplo com hash no /etc/shadow do linux

fulano:$1$dawdgsad$sALDKA~DDAWLSfawfsahgkul:130422:0:99999:30:::


Estrutura:

user :$
algorítmo $
sal $
output hash :
ultima data de modificação :
mínimo de dias para liberar modificação de senha :
máximo de dias para liberar modificação de senha :
dias para avisarexpiração da senha :
dias de bloqueio após senha expirada 
expiração da conta
```


***Charound*** também é outra técnica para evitar rainbow tables e brute force. Baseia-se em aplicar o hash múltiplas vezes ao invés de só uma vez, aumentando em muito a complexidade assintótica de adquirir os padrões comuns de rainbow table.




