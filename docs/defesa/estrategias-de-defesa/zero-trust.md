# Zero Trust Arquitecture / Arquitetura de Confiança Zero (ZTA)

Até alguns anos atrás, a segurança cibernética se baseava muito numa abordagem tradicional de segurança baseada em perímetro/borda. Protegia-se as fronteiras de acesso ao sistema fortemente e tudo que passasse a fronteira era considerado confiável. Era uma abordagem parecida com a segurança física que normalmente coloca uma cofiança muito maior nas pessaos dentro das instalações a serm protegidas.

O Zero Trust é uma mudança de postura dessa segurança em perímetro/borda. Sua filosofia principal é não acreditar automaticamente em ninguém, esteja o recurso para dentro ou fora da fronteira de confiança.

O *paper* completo que explica sobre essa arquitetura pode ser encontrada no [NIST 800-207](https://www.nist.gov/publications/zero-trust-architecture).

## Princípios

Normalmente o Zero Trust se baseia a partir das seguintes práticas:

- **Least Privilege Access**: dar a menor quantidade de permissões e poder aos usuários, limitando-se somente às permissões estritamente necessárias. "Se tudo que ele precisa é ler o documento, não o dê acesso a escrita".

- **Micro-segmentação**: dividir nossa rede em vários pequenos grupos protegidos por firewalls e outras defesas de borda. Em caso de invasão a um perímetro, uma rede micro-segmentada só daria acesso a uma pequena parte da rede ao atacante.

- **Monitoração Contínua**: monitorar todos os usuários e recursos, independente deles estarem dentro ou fora do perímetro.

- **Autenticação de Múltiplos Fatores (MFA)**: autenticação que exija mais de um fator. Será melhor explicado no capítulo de Identidade.

- **Verificação da Identidade do Usuário e do Dispositivo**: não é só porque um usuário está dentro do perímetro que ele realmente é quem diz ser. Pode haver falsificações.

- **Criptografia**: mesmo se um ator malicioso invadir o sistema, ele não conseguirá entender a informação.

- **Controles de Acesso Restritos**: dar somente o acesso necessário.

- **Assumir a Possbilidade de Ataques**: entender que em cybersecurity, todo recursos, sistema e usuário podem estar sofrendo ataques e tendo suas informações e conexões abaladas. Assuma que todos podem ser um ator malicioso.


## Estrutura

![ZTA](assets/ZTA.png)

A imagem mostra como é a estrutura da ZTA, junto a algumas práticas que estão dentro dela. Por enquanto, vamos olhar somente para os dois planos que o ZTA provê na imagem:
- Data Plane
- Control Plane

Vamos supor que um usuário deseja acessar um recurso. No Data Plane, o sujeito, através de um sistema cliente, enviará a requisição de acesso ao **Policy Enforment Point (PEP)**. Essas informações são consideradas não confiáveis por padrão e portanto precisam provar sua confiança. Para isso, o PEP envia a requisição para o Control Plane, mais especificamente para o **Policy Decision Point (PDP)**. O PDP possui uma engine de políticas pré determinadas por um administrador de políticas e essas políticas vão determinar se a requisição, o usuário e o seu dispositivo são confiáveis. A resposta é enviada de volta ao PEP e, se a resposta foi que os sujeitos são confiáveis, uma confiança é criada e o acesso ao recurso é dado.

Apesar de ser um modelo relativamente simples, várias práticas apoiam essa arquitetura. Entre eles estão:

- **Continuous Diagnostic and Mitigation (CDM) System**. Melhor explicado nos capítulos de defesa cibernética.
- **Industry Compliance**. Melhor explicado no capítulo de compliance
- **Threat Intelligence**. Melhor explicado nos capítulos de Threat Intelligence.
- **Logs de Atividades**. Melhor Explicado nos capítulos de Logs
- **Políticas de Acesso a Dados**. Melhor explicado nos capítulos de Identidade.
- **Public Key Infrastructure (PKI)**. Melhor explicado nos capítulos de infraestrutura.
- **Gerenciamento de ID**. Melhor explicado nos capítulos de Identidade.
- **System Incident and Event Management (SIEM)**. Melhor explicado nos capítulos de defesa cibernética.