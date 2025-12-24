# Condições de Corrida

Um fator essencial para execução de programas é a ordem de execução dos procedimentos. Em muitos modelos de programação, como programação paralela, cada procedimento estará disputando com os outros para conseguir os recursos do processador e memória. Essa disposição criará "condições de corrida" entre eles.

Apesar desse sentido geral, o termo é normalmente empregado quando essa corrida por recursos apresenta possibilidades de resultados que permitam com que os procedimentos sejam executados em ordens incorretas, ordens que causem comportamentos indesejados. Existem várias formas de disputas entre recursos, algumas mudando o procedimento a ser executado entre instruções (nível assembly), sem nem deixar o procedimento terminar.

## Time of Check to Time of Use (TOCTTOU)

Quando um atacante ganha acesso antes de uma checagem de autenticação, é possível que ele consiga inserir código ou alterar o que já está lá para causar uma mudança no comportamento que atrase a checagem de autenticação, mas adiante o procedimento responsável por autorizar o usuário (que só seria originalmente chamado se a checagem de autenticação fosse verdadeira). Como consequência, o adversário ganha acesso ao usuário mesmo que ele não seja quem realmente diz ser.

Dentre as vantagens desse ataque para um adversário, há a de impedir com que *resets* de senhas sejam capazes de impedir seu acesso.

## Time of Evaluation

Quando duas ou mais threads ou processos acessam e modificam um mesmo recurso global. As threads/processos escolhidos para execução podem ser mudadas a qualquer momento e no meio de qualquer instrução (nível assembly). Quando ocorre uma mudança da thread/processo e execução, também ocorre uma **troca de contexto** das **variáveis locais** e **funções locais**, entretanto os **recursos globais** continuam os mesmos. Se uma thread 1 quer usar o valor de uma variável global como A e uma thread 2 entrar em execução e mudar a variável para B, quando a thread 1 ganhar novamente o tempo de execução, ela usará o valor da variável como B. Se não for bem planejado, essa condição de corrida pode causar resultados indesejados ao programador e ao usuário dependendo do tempo em que ocorrerem as trocas de contexto. O resultado fica dependente do *timing* das threads e processos.