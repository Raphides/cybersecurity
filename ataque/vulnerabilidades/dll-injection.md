## Injeção de DLL

(Antes de ler essa seção, leia sobre [DLLs](ataque\vulnerabilidades\intro.md#DLL).)

Injeções DLL focam em injetar DLLs em outros processos sendo executados. A ideia para se realizar um ataque de injeção de DLL é:
1. acessar o processo
2. alocar memória dentro daquele processo,
3. copiar o caminho da DLL ou a própria DLL na íntegra para a memória alocada.
4. determinar corretamente o endereço de memória em que a DLL foi alocada.
5. forçar o processo a executar a DLL na memória alocada.

É possível realizar um ataque desses com o Metasploit.

Saiba mais:
- https://attack.mitre.org/techniques/T1055/001/