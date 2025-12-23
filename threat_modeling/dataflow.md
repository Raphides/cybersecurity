# Diagrama de Fluxo de Dados (DFD)

Um DFD é um diagrama que mapea o fluxo de dados através de um sistema. Ele é simples e muito comum, porque pode ser usado para:
- Compreender o funcionamento da aplicação
- Descrever e detalhar a arquitetura do sistema 
- Servir de base para **modelagem de ameaças**

## Criando um DFD

Criar um DFD é simples e não necessita de ferramenta especializada. Você pode até mesmo criá-la à lápis.

Entretanto, antes de criar qualquer DFD, é necessário definir o **escopo** do seu diagrama. **O nível de abstração de um DFD não é fixo e portanto deve ser ajustado ao projeto**. Não é interessante que um DFD detalhe demais elementos que não precisa detalhar para a modelagem de dados. Assim como não é interessante e ele abstraia processos importantes a serem analisados.

## Elementos de um DFD

**Processo**: normalmente representado por um retângulo com vértices arrendondadas. Descreve um ou mais transformações ou tratamentos de dados. Exemplo: recebimento de requisições HTTP.

![Imagem]()

**Fluxo de Dados**: normalmente representado por setas, indicando que elemento distribui e que elemento recebe os dados. Várias setas de fluxo de dados estão presentes em um DFD. Exemplo: input do usuário para o servidor web HTTP.

![Imagem]()

**Entidade Externa**: representados por retângulos com vértices pontiagudos. Descrevem agentes fora do sistema estudado ou processos cuja atuação nos dados não é completamente controlada ou conhecida. Exemplo: usuário. Através dos elementos externo e processos, o nível de abstração do DFD pode ser controlado.

![Imagem]()

**Armazenamento**: Representado por duas linhas horizontais e paralelas, com o nome do dispositivo armazenador entre elas.

![Imagem]()

**Fronteira de Confiança**: representada for uma linha pontilhada, a fronteira de confiança separa entidades com diferentes níveis de confiança pelo sistema. Por exemplo: é justo separar o nível de confiança de um admnistrador e usuário caso for interessante ao seu DFD. Também é comum incluir uma fronteira para separar o que se considera internet e o que é considerado processamento interno.

![Imagem]()