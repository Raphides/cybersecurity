# Defesas para ADs

## Modelo em camadas (tiering)
Controle destinado a impedir escalamento de privilégios vertical. O controle separa as máquinas e contas na empresa em 3 tiers (tier 0 a tier 2). Contas de tiers mais acima (tier 0 é o mais alto) nunca podem entrar/fazer login/rebaixar-se ao ambiente dos tiers mais abaixo. Dessa forma, caso máquinas dos tiers mais abaixo estejam comprometidas, a conta de tier mais alto não será comprometida ao entrar em um computador já comprometido.

OBSERVAÇÃO: máquinas de tier mais baixo ainda podem chamar máquinas de tier mais alto, mas só chamar e retornar. 


Vários mecanismos precisam ser acionados para transformar o modelo em camadas uma realidade. Entre elas:
- Políticas de Grupo: principalmente para impedir login de tiers mais altos em máquinas e contas de tier mais baixo.
- PAW (Privileged Access Workstarion): máquina específica em que é permitido login por contas de tier 0.
- LAPS + 2FA

![]()


### Tier 2
Pode acessar recursos de camadas superiores, mas nunca administram nada de camadas acima.

### Tier 1
São todas aquelas máquinas e contas que não são nem tier 0 e nem tier 2. Normalmente seu comprometimento permite movimentação lateral e algum poder sobre algum conjunto específico de recursos.

Exemplos de máquinas tradicionalmente de tier 0:
- Contas Administradoras
- Máquinas Adminstradoras
- Grupos Administradores
- Servidor de Banco de Dados
- Servidor de Arquivos
- DFS
- Servidores Web
- Contas de usuário administradoras de áreas específicas (segmentação).

### Tier 0
Máquinas que podem diretamente comprometer todo o domínio se acessados pelo atacante.

Exemplos de máquinas tradicionalmente de tier 0:
- Contas Administradoras de Domínio (DA)
- Controladores de Domínio (DC)
- CA
- PKI
- Lithnet Access Manager (LAM)
- VMware vCenter
- Servidor de Backup

Para classificar corretamente quais ativos são tier 0, considere usar a tabela: https://specterops.github.io/TierZeroTable/

A SpectreOps é amplamente conhecida no meio de segurança de EAD.


## Microsoft Windows LAPS + 2FA
Antes do LAPS, todas as máquinas do domínio que tinham um admnistrador local possuiam a mesma senha para essa conta. Logo, ao descobrir a senha de administrador local de uma máquina, era possível escalar privilégios para administrador da máquina e mover-se lateralmente através das máquinas.

Atualmente há duas versões mais relevantes do Windows LAPS, a legada e a nova.

O LAPS legado, ao instalar, muda o esquema de dados do AD ao criar 2 novos atributos para criar senhas únicas para cada administrador e com tempo de expiração.

O novo Windows LAPS exige um sistema operacional mais atual (>= Windows 10 e >= Windows Server 2019)