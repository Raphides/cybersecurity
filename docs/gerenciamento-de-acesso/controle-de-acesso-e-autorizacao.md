# Modelos de Controle de Acesso e Autorização

Autorização é o que determina quais direitos e permissões um usuário possui num sistema. "Eu, administrador, autorizo usuário X a entrar nessa página secreta" é uma frase que ilustra muito bem o que seria autorização.

Atualmente, o modelo geral de como as autorizações são dispostas em um sistema é decidido através do modelo do controle de acesso utilizado.

Modelos de controle de acesso definem como os sistemas de controle de acesso organizam e gerenciam seus acessos, assim como as permissões definidas a cada usuário. Muitos modelos ou conceitos desses modelos podem ser usados em conjunto para criar um sistema de controle de acesso e autorização mais robusto.

## DAC - Discretionary Access Control

Cada usuário tem poder para gerenciar os privilégios de seus recursos no sistema. Ou seja, a administração descentralizada.

Você pode ver um exemplo ao olhar o Google Drive. Cada usuário pode gerenciar as permissões que outros usuários têm sobre seus próprios documentos e slides. É possível até mesmo transferir a sua própria posse dos arquivos a outros usuários.

Apesar de descentralizado, DAC é um modelo massante aos usuários, já que eles normalmente têm que editar a lista de usuários permitidos e permissões associadas a eles. Dependendo de como essas listas de controle de acesso são apresentadas no sistema e de como é a granularidade das permissões, os usuários podem passar tempo demais editando as listas.

## MAC - Mandatory Access Control

Os privilégios de administração são centralizados num pequeno grupo de administração do sistema, podendo ás vezes até ser reduzido a somente uma pessoa. Essa administração centralizada é a única capaz de determinar o nível de acesso de cada usuário, impedinddo que o próprio usuário tenha autonomia sobre o nível de acesso próprio e dos outros sobre seus recursos no sistema.

Um exemplo seria os níveis de confidencialidade de documentos: confidencial, sensível, livre. Cada usuário recebeu acesso a certos níveis de confidencialidade e não tem como mudar seu nível por si mesmo ou ver documentos com confidencialidade acima do que lhe é permitido acessar.

Logo um MAC é ótimo para organizações com muita segurança em mente, como instalações militares e instituições financeiras. Em contrapartida, não é uma boa escolha para empresas que precisam de uma flexibilidade maior e mais ágil de suas permissões.

## RBAC - Role Based Access Control

Os administradores de sistema separam tanto os privilégios de funcionalidades no sistema, quanto os privilégios de administração, e os distrubuem em papéis. Papéis são conjunto de permissões associadas a alguma função exercida na empresa. Dessa forma, papéis são distribuídos aos funcionários e vão determinar o que eles podem ou não realizar no sistema.

Quanto mais granular as permissões forem, mas úteis e precisos serão os papéis criados.

Esse tipo de modelo traz maior prático, visto que, para atualizar as permissões de um usuário, não é preciso adicionar e retirar privilégio por privilégio, somente seus papéis. Um funcionário que sai de sua unidade por exemplo só precisa ser retirado do papél referente as permissões de sua unidade.

## RuBAC - Rule Based Access Control

O acesso a recursos é determinado através de regras de acesso. Qualquer usuário que alcançar as condições das regras recebe privilégios sobre o recurso.

Por exemplo: um recurso só aceita acesso através de um usuário com uma conexão de um dispositivo mobile.

É comum utilizar essas listas de regras junto ao RBAC.

## ABAC - Attribute Based Access Control

Um usuário tem acesso a recursos se ele possuir os atributos/características exigidas pelo recurso. Essas caracetrísticas podem ser hora do dia, tempo atual, cargo na empresa, localização, etc.

Por exempo: um recurso só pode ser acessado por funcionários sêniores.

Esse tipo de modelo é mais flexível, mas é pouco prático. Não dá para gerenciar tantas condições de acesso por atributo ao possuir vários recursos disponíveis.

----

Para mais detalhes e modelos, veja: https://nordlayer.com/learn/access-control/types-of-access-control/