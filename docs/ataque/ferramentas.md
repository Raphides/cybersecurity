# Ferramentas de Pentest
## Web Pentest - Ferramentas completas
- Burp Suite
- OWASP ZAP

### Funcionalidades:
- **Web-Proxy**: 
- **Spider** (crwaling)
- **Scanner**: análise de vulenrabilidades
- **Intruder**: ataques personalizados
- **Repeater** (modificação de requisições)
- **Encoder e Decoder**: transformação de dados usando bases e codificações conhecidas.

### Modos
- **Modo passivo**: finge ser um usuário comum, buscando informações disponíveis da página e vulnerabilidades. Aqui agem muito as funcionalidades de Spider, Repeater, Decoder, Encoder e até alguns Scanners discretos.
    - **Legabilidade**: cada caso é um caso. Procure as regulações do serviço analisado e busque altorizações. Caso não tenha altorização, não faça. Caso não saiba se tem, não é recomendadoao menos limite-se a ferramentas não danosas de pura análise e só realize ações que não demonstrem intenção de ataque.
    - **Ferramentas exclusivas**: Shodan
- **Modo ativo**: 


## Reconhecimento Intrusivo - Pentest

Mapeamento da página, conexões e rede.

### Desvantagens
- Inseguro ao atacante e ao alvo.
- Lento.

### Ferramentas
- Webproxy
- Fuzzy
- nmap

## Scan de vulnerabilidades
### Ferramentas
- Nikto


## Problemas com o Ajax
Quando muitas ferramentas foram criadas, as páginas eram mais inseguras, com boa parte da lógica estando disponível ao próprio cliente. Um curl resolvia boa parte do spider e scanner, mas hoje em dia esconde-se boa parte da página ao usar scripts que criam os elementos em Runtime. Isso dificulta o pentest e o uso de muitas ferramentas antigas.