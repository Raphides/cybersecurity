# Metasploit

Ferramenta de propriedade da Rapid7. Ajuda na criação de *exploits*.

**Vocabulário:**

- Exploits: código que explora uma vulnerabilidade existente num sistema.
- Payload: a carga útil se refere ao conteúdo que de fato vai explorar a vulnerabilidade num exploit. É o conteúdo, o código malicioso.
    - Payload Direto: vai até a porta.
    - Payload Reverso (mais comum e poderoso): arruma uma forma do alvo mandar o acesso a porta para a gente. Mais fácil de atravessar um firewall.
- Remote Host (RHOST): computador alvo.
- Local Host (LHOST): Host a receber a conexão de volta, ou seja, o nosso IP na maioria das vezes.
- Remote Port (RPORT): porta alvo do computador alvo.
    - Foque em portas essenciais. Exemplo: portas 80, 443 e 53 nunca estarão fechadas, porque mexem com TCP / HTTP e UDP / DNS. Sem eles ativados, o 

## Merterpreter
Ferramenta de trojan do Metasploit que permite o acesso remoto ao computador alvo. Você pode configurar alguns elementos payload para adaptar o ataque a máquina alvo e aos softwares utilizados.