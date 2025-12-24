# Tecnologias de Detecção Disruptivas - Honeypots

São armadilhas para hackers, uma isca de fato. É um sistema feito propostitalmente para atrair os atacantes, esperando suas tentativas de ataque e invasão. Os honeypots fazem parecer que têm informações sensíveis ou confidenciais, além de demonstrarem ter em sua proteção interna algumas vulnerabilidades propositais para serem exploradas pelos hackers.

Essas máquinas posuem um monitoramento gigante para estudar com atenção as técnicas e procedimentos dos atacantes que caem na armadilha.

Um honeypot deve ser feito com o maior cuidado, já que se não for propriamente isolado, pode gerar danos fora do honeypot. Por isso um honeypot normalmente é isolado em uma DMZ própria, com um monitoramento extenso e discreto de atividades. 

Ferramentas conhecidas de honeypot
- Cowrie: SSH honeypot escrito em Python que simula um Bash Linux.

## Mail honeypot

É um endereço de email armadilha. Ele é enviado em lugares que possivelmente rastream os emails e incluem a conta em listas de phishing. Assim, é garantido que os emails recebidos nessa conta muito provavelmente são phishing.

## Database honeypot

Uma base de dados normalmente parecida com a arquitetura parecida com a base de dados em produção. Ela é liberada sem informações cruciais a fim de receber pentestes e ataques hackers para melhorar a proteção da base em produção.


## Malware honeypot

Aplicativos e programas criados especificamente para atrair ataques de malwares e rastrear suas ações.

### Spider honeypot

Websites que visam rastrar *spiders* (rastreadores web)

## Honeneyfile

Arquivos individuais com o propósito de atrair atacantes para depois monitorar seus comportamentos.

## Honeynet

Honeypots em alta escala. Uma rede inteira configurada para atrair atacantes e monitorar suas atividades. Dessa forma, ela é composta por vários equipamentos e servidores.

## Honeywall

Firewall configurado propostitalmente para atrair atacantes e monitorar suas atividades. Bem comum na borda de Honeynets. É comum que esses firewalls tenham vulnerabilidades suficientes para permitir a passagem do atacante, mas não sem monitorá-lo e realizar a captura, controle e análise de seus dados.

A análise de dados costuma ser feita em conjunto a um servidor de gerenciamento de dados. É comum que essa análise envolva a inspeção de pacotes e podemos dividi-la em 3 tipos:

- Rasa: Shallow Packet Inpsection (SPI)
- Média: Medium Packet Inspection (MPI)
- Profunda: Deep Packet Inspection (DPI)

A inspeção rasa (SPI) costuma se limitar a inspecionar o cabeçalho do pacote. Já a inspeção média (MPI) trabalha com mais metadados do pacote além do cabeçalho. Por fim, a inspeção profunda (DPI) costuma para os cabeçalhos, metadados e o próprio conteúdo do pacote.