# Honeypots

São armadilhas para hackers, uma isca de fato. É um sistema que atrai os atacantes e espera suas tentativas de ataque e invasão. Um honeypot deve ser feito com o maior cuidado, já que se não for propriamente isolado, pode gerar danos fora do honeypot.

Por isso um honeypot normalmente é isolado em uma DMZ própria, com um monitoramento extenso e discreto de atividades. Entretanto sua proteção interna costuma ter vulnerabilidades propositais para serem exploradas pelos hackers.

## Tipos de Honeypots

### Mail honeypot

É um endereço de email armadilha. Ele é enviado em lugares que possivelmente rastream os emails e incluem a conta em listas de phishing. Assim, é garantido que os emails recebidos nessa conta muito provavelmente são phishing.

### Database honeypot

Uma base de dados normalmente parecida com a arquitetura parecida com a base de dados em produção. Ela é liberada sem informações cruciais a fim de receber pentestes e ataques hackers para melhorar a proteção da base em produção.


### Malware honeypot

Aplicativos e programas criados especificamente para atrair ataques de malwares e rastrear suas ações.

### Spider honeypot

Websites que visam rastrar *spiders* (rastreadores web)


## Ferramentas conhecidas de honeypot
- Cowrie: SSH honeypot escrito em Python que simula um Bash Linux.

