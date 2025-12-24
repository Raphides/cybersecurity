# Ataques a partir do vetor humano

## Engenharia Social
Engenharia social caracteriza-se como a manipulação das pessoas para que revelem informações sensíveis e importantes ou realizem ações. Os benefícios incluem:
- advinhar senhas fracas.
- ganhar a confiança da vítima para que ela posteriormente baixe as defesas ao ator malicioso ou revele ainda mais informações.

Mais detalhes em:
- https://en.wikipedia.org/wiki/Social_engineering_(security)


## Ataques de Falsificação (Spoofing)
Um ator malicioso finge ser de uma fonte confiável, normalmente com a intenção de evadir as defesas de um sistema e consequentemente ganhar momentaneamente a confiança da vítima. Um exemplo comum é falsificar a origem do email para endereços de email confiáveis.

Mais detalhes em:
- https://en.wikipedia.org/wiki/Spoofing_attack
- https://attack.mitre.org/versions/v17/techniques/T1672/


## Personificação
O ator não só finge ser uma fonte confiável, como a incorpora. Técnicas de engenharia social é muito mais utilizada do que na falsificação. A intenção não é só evadir a defesa, como principalmnte ganhar a confiança do usuário. 

Exemplo da diferença entre ambos: um ataque de email pode usar do *email spoofing* para trocar seu endereço de origem e metadados, enganando os sistemas de defesa e um pouco o usuário, como também pode usar o *email impersonation*, mostrando um email idêntico ao da fonte que está fingindo ser.

Mais detalhes:
- https://attack.mitre.org/versions/v17/techniques/T1656/


## Phishing
É o ataque de "pescar dados sensíveis" de um usuário, como usernames, senhas, tokens, etc. Os exemplos mais clássicos de phishing são emails com links que redirecionam a vítima para sites falsos. Enquanto esse ataque não é a enganação do humano em si como os outros ataques, phishing normalmente utiliza-se muito de engenharia social, personificação, falsificação e mascaramento/ofuscação para convencer seus usuários a passarem seus dados nesses sites falsos.

Phishing é extremamente comum e não há uma solução sólida para lidar com esses ataques.

Phishing é divido em diversas categorias, algumas mais famosas e outras menos famosas.

Por escopo:
- **Spearphishing**: phishing direcionado especificamente a uma empresa ou indivíduo específico. Essa categoria existe porque o phishing tradicional era muito difundido através de SPAMs e por consequência suas linguagem e estratégia eram mais genéricas, sendo mais simples de se perceber o golpe e capturando poucos usuários. Ao ser direcionado, o spearphishing costuma ser mais especializado e convincente por ter mais informações sensíveis e específicas para trabalhar. Não só isso, como ataques direcionados indicam que alguém está querendo especificamente causar mal àquela vítima, o que pode indicar até mesmo cadeias de ataque mais especializadas e específicas ao ambiente da vítima. Como resultado, esse phishing ganha uma notoriedade e taxa de sucesso maior.

- **Whaling**: ao invés de se pescar peixes pequenos, pesca-se baleias! É um phishing voltado para nomes "grandes". Enquanto a definição de "grande" pode ser variável, o termo normalmente se refere a CEOs, CFOs, chefes em geral dentro de uma indústria específica.


Por payload:
- **Phishing por Links**: o phishing contém links. Esses podem ser maliciosos por si (comandos ofuscados) só ou redirecionarem para um site malicioso.
- **Phishing por Arquivos**: o phishing contém um arquivo malicioso. No final, o arquivo malicioso irá de alguma forma garatir informações sensíveis ao ator malicioso, seja através de código malicioso ou de redirecionamentos do arquivo.

Por vetores:
- **Email Phishing**: phishing via email. Alguns também o chamam de Email Spoofing (falsificação de email), dado como ataques de falsificação de email e phishing normalmente andam juntos. 
- **Smishing**: phishing via SMS.
- **Vishing**: phishing via ligação/gravação/voz. Eles fingem ser alguém através de ferramentas de modificação de voz e inteligência artificial.

Mais detalhes em:
- https://attack.mitre.org/versions/v17/techniques/T1566/
- https://attack.mitre.org/versions/v17/techniques/T1598/
- https://attack.mitre.org/versions/v17/techniques/T1534/
- https://www.trendmicro.com/en_us/what-is/phishing/types-of-phishing.html

## Mascaramento / Ofuscação / Ocultação
Ocultar elementos e dados maliciosos para que pareçam legítimos. Há várias técnicas de ocultação/mascaramento, como vistas na [Introdução a Criptografia](.\criptografia\intro.md). Essas técnicas são utilziadas em vários contextos e enquanto naquela seção, era usada para proteger, aqui suas técnicas (criptografia, esteganografia, etc) são usadas para atacar. Mascaramento pode ser usado tanto para enganar o vetor humano, como para enganar as defesas do sistema.

Exemplos: codificar um link malicioso de phishing.
Mais detalhes:
- https://attack.mitre.org/versions/v17/techniques/T1036/
- https://attack.mitre.org/versions/v17/techniques/T1027/

## Watering Hole Attack / Drive-By Compromise

É um ataque comum, sofisticiado e direcionado. Dado que um site normalmente possui um público específico que o visita, os atores maliciosos, quando possuem alvos, procuram sites vulneráveis que seus alvos irão muito provavelmente visitar e o exploram. É um ataque que explora a confiança das pessoas em sites comuns a certo nicho e o interesse por certos assuntos.

O processo típico é:
1. Um usuário visita um site legítimo infectado por malware. Essa infecção pode acontecer de diversas formas, normalmente sendo ou por injeção de código e script malicioso, ou por anúncios com código malicioso.
2. O malware analisa o computador do usuário em busca de softwares com vulnerabilidades e brechas.
3. Ao encontrar vulnerabilidades ou brechas, exploits (código malicioso que exploram as vulnerabilidades encontradas) são enviados ao computador do usuário.

Referências:
- https://attack.mitre.org/techniques/T1189/

## Typo Squatting / URL Hijacking

Adversários se aproveitam do fato das pessoas ocasionalmente realizarem typos (pequenos erros de grafia) para registrar recursos com esses typos e a partir disso, encadear com outros ataques.

Por exemplo, é muito comum escrever goggle.com ou gogle.com ao invés de google.com. Um adversário registraria um site malicioso em goggle.com (typosquatting), criaria uma interface idêntica ao login (personificação, phishing) do google e esperaria o usuário por engano entrar em seu domínio e realizar login para roubar as credenciais. Outro exemplo comum é só criar uma cópia do site, mas com uma bomba de anúncios.

