# Buffer Overflow

(Antes de ler essa seção, leia sobre [DLLs](ataque\vulnerabilidades\intro.md#Overflow).)

Uma aplicação comum da ideia de overflow é o buffer overflow. Ela ocorre quando o buffer/vetor/lista recebe um valor maior do que é capaz de armazenar. Como consequência imediata, a memória em excesso é armazenada em memória adjacente. Dada a natureza da diposição do computador de posicionar novos dados em memória adjacente, normalmente um buffer overflow acaba sobrescrevendo os dados na memória, gerando desde comportamentos inesperados até interrupções no funcionamento do software.

É muito comum que buffer overflows causem a sobrescrita de dados de endereços de jumps.