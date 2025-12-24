## Network Control Access

## Pontos de Estrangulamento
Identificar (ou fabricar) pontos críticos em um sistema para concentrar suas defesas (ou ataques).

Exemplo: construções costumam limitar a entrada e saída de pessoas a somente poucas passagens. Essas passagens podem ter portas para controlar o fluxo e pessoas seguranças para evitar a entrada de pessoas indevidas.

## Arquitetura Zero Trust
Planejamento de sistemas minimizando ao máximo a confiança o usuário. Essa abordagem normalmente é adquirida através de:
- Permissões segregadas
- Funções segregadas
- Permissões por papéis a serem pedidos.
- Novos usuários do sistema começam sem quaisquer papéis.

## Princípio do Mínimo Privilégio

## Defesa em Profundidade
Garantir a defesa ao pôr uma série de camadas defensivas ao seu sistema.

## Falhar de forma Segura (Fail Safe)
Permitir que falhas no software ocorram de forma segura:

* Erros que não revelem nosso código (stack trace) ao cliente, para não revelar informações internas da aplicação.
* Erros que continuem ao menos parcialmente funcionando mesmo com exceções.
* Erros que não levem a comportamentos alternativos não seguros. 

## "Não é se seremos atacados, é quando"
Preparar-se para ataques e falhas, independente do quão robusta sua segurança pareça.

## Obscuridade (Security by Obscurity)
Controle de exposição do funcionamento do seu sistema ou negócio. A obscuridade em si emprega mecanismos e métodos para esconder esse funcionamento e evitar a exposição excessiva das informações do sistema.

Enquanto é uma estratégia famosa, muitos são contra o uso dessa estratégia. Uma segurança que necessita de obscuridade para funcionar normalmente é em razão de uma segurança frágil.

## Segurança Ágil
- A equipe de segurança deve responder rapidamente a ameaças e deve ter a liberdade de agir e depois perguntar.
- A segurança deve ser simples, fácil e rápida de implementar

## Segurança por Definição/Padrão (security by default)
Garantir a segurança deve ser o padrão de qualquer sistema.

Muitos sistemas vem com as configurações de fábrica menos seguras. Vejamos por exemplo um firewall, que pode vir aceitando todas as requisições estranhas em sua configuração padrão. A abordagem de Segurança por Definição defende que os sistemas deveriam vir bloqueando pedidos e respostas estranhas como padrão. Portanto, ao receber um equipamento, o padrão deveria ser conferir as configurações e mudar você mesmo as configurações para seguro caso o equipamento não venha seguro por padrão.

A escolha de linguagens, funções e bibliotecas seguras durante o ciclo de desenvolvimento também é parte da segurança por padrão.

Obviamente esse tipo de abordagem não se aplica muito bem em todos os casos e deve ser avaliado junto com a usabilidade e desempenho para garantir um sistema eficiente.

## Deny By Default

## Análise de Lacunas (*Gaps Analysis*)

Processo da avaliação do que uma empresa é agora em comparação ao que ela almeja/deveria ser no contexto de medidas e postura de segurança.

O resultado normalmente é a identificação de lacunas entre a expectativa e a realidade. Essas lacunas se resumem em vulnerabilidades, fraquezas e oportunidades de melhoria. Posteriormente, as lacunas podem ser usadas como insumo para um plano de aprimoramento da segurança na empresa/instituição.