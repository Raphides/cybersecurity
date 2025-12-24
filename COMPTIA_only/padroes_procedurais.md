# Padrões Procedurais

Relativo aos padrões procedurais que um profissional de segurança pode lidar no seu dia a dia, seja em relação a processos de negócios, aprovações, dia-a-dia, operações, documentação ou controle de versão. Conceitos, explicações e ferramentas são descritas nesse módulo para ajudar o leitor a lidar com esses processos.

## Processo de Aprovação
Processo em que uma ação, atividade ou decisão é levada para ser aprovada ou não dentro de uma empresa. Normalmente quem aprova são aqueles que detém mais responsabilidade na empresa, ou seja, as pessoas de maiores cargos.

Um processo de aprovação padronizado tende a permitir uma tomada de decisão mais veloz e certeira. Normalmente um processo de entiquetagem é utilizado no processo de aprovação, com cada pedido de aprovação sendo um tíquete. Utilizando um sistema padronizado assim, independente de ser manual ou aprovado, é necessário uma série de recursos, como:
* Cadeia de aprovação.
* Detalhes suficientes exigidos no tíquete.
* Processo de notificação.
* Revisão global de mudança.
* Notificação/Tratamento de Colisão sobre mudanças.

É necessário que **donos** e **stakeholders** (ao menos os mais críticos para essa decisão) estejam envolvidos no processo de aprovação e em sua revisão. **Análises de impacto** devem ter seus riscos avaliados e notificados a todos esses envolvidos, assim como os **resultados de teste**, caso testes ocorram.

## Donos
Em empresas grandes, um ou mais funcionários normalmente são "donas" de  um processo ou ferramenta. Um processo de posse bem definido notifica os donos dos processos e ferramentas toda vez que alguma mudança na empresa impacta aquilo que possuem.

## Parte Interessada (Stakeholders)

Stakeholders são a parte interessada em relação às empresas e produtos e, de forma mais formal e restrita, são normalmente aqueles que os financiam. Eles podem ou não possuir a empresa ou serem donas do produto. Empresas maduras notificam seus stakeholders sobre mudanças e notícias que podem impactar suas decisões de modo a estabelecer e manter uma relação de confiança.

## Análise de impacto

Toda ação ou possível ação (interna e externa) numa empresa deveria acompanhar análises de impacto. Uma análise adequada lista quais sistemas podem ser afetados pela mudança, o nível de impacto e melhor e pior cenário resultantes.

## Resultados de Teste
É possível realizar testes e incluir seus resultados na análise de impacto. Incluir o nível de dificuldade da ação a partir dos testes e procedimentos de roll-back.

## Janela de Manutenção
Definir e notificar aos interessados sobre a/o/as/os:
* duração de tempo estimada de manutenção
* intervalo de horário em que ocorre
* procedimentos de validação
* procedimentos de roll-back
* critério de sucesso

## Standard Operating Procedures (SOP)
Toda mudança e decisão possui procedimentos listados no *Method Of Procedure* (MOP). Já o SOP possui todas as informações e conceitos ditos nesse módulo, inclusive o MOP.

Um SOP lista uma série de procedimentos ou ao menos direções para seguir sobre como os procedimentos são feitos naquela empresa.

## Implicações técnicas
Conceitos, procedimentos e recursos relacionado a implicações técnicas.

- Listas de Permissão/Recusa: Listas de pessoas, sistemas, itens e outros elementos permitidos ou não em um contexto ou local devido a implicações técnicas.
- Atividades Restritas: atividades que possam necessitar de autorização prévia de alguém mais em cima na cadeia hierárquica para ser realizada.
- Downtime:
    * Planejada: mais comum em janelas de manutenção e por isso devem ser previamente comunicadas.
    * Não Planejada.
- Service/App Restart: um restart pode demorar muito tempo em alguns sistemas e portanto precisam ser consideradas e notificadas.
- Aplicações Legadas: aplicações que poderiam ter suas tecnologias ou metodologias por outras mais adequadas. Normalmente aplicações legadas são antigas e muitas empresas não planejam trocá-las visto que a dificuldade técnica para isso pode ser alta e os riscos altos.
- Dependências: serviços, aplicativos, tecnologias e técnicas dos quais o seu produto depende. São os lugares dos quais o seu produto tira informação e envia informação.

Se o seu produto, como um banco de dados, for uma dependência de um produto que outro departamento está trabalhando, lembre-se que mudanças no seu produto devem ser notificadas.

## Documentação
Deve ser regularmente atualizada em tempo real, ou ao menos o mais próximo que conseguir a partir da implementação das modificações. Sejam diagramas que foram atualizados ou políticas que foram redigidas.

## Controle de Versão
Salva as mudanças geradas num projeto e portanto é uma ótima estratégia de roll-back. Normalmente utilizada em DevOps. Costuma salvar cada versão através de um padrão de versionamento. O mais comum é:

x.y.z

x = número de versão maior. Esse número aumenta conforme mudanças críticas e grandes são realizadas no projeto. Mudanças de arquitetura, novas grandes adições de capacidades são exemplos de mudanças assim.
y = número de versão menor. Esse número aumenta conforme menores mudanças são realizadas no projeto. Pequenas adições e exclusões de recursos e capacidades são exemplos de mudanças assim.
z = número de versão que representa uma atualização para corrigir bugs.
