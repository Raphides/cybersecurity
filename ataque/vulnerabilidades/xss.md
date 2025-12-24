## Cross Site Script (XSS)

XSS é um ataque de injeção de scripts Javascript maliciosos em um website ou web app. XSS podem ser ataques simples, ou ataques bastante elaborados e eficientes quando baseados na análise das tecnologias, códigos e padrões utilizados em um website. Por isso XSS e os demais ataques de injeção continuam como alguns dos ataques mais preocupantes até hoje.

Para o XSS acontecer, precisamos de campos vulneráveis que aceitem a execução de um javascript. Por exemplo: por que não testar se barras de pesquisa aceitam um de HTML? Um `<b>camisa polo</b>` se for interpretado como **camisa polo**, omitindo as tags, pode representar alguma vulnerabilidade. O que impediria de eu inserir um `<script>`? Estude o site, veja se a sua estrutura faz parecer que ele é vulnerável a esse tipo de ataque.

Quer ver na prática ataques XSS? Vá no site Port Swigger e resolva os laboratórios de XSS lá dentro.


### XSS Refletido

É um ataque XSS que visa a injeção de scripts no lado do cliente, enviando a página infectada para algum alvo via phishing.

Voltando ao exemplo da barra de pesquisa, se a pesquisa for feita, como `site.com/search?termo+de+pesquisa`, não seria difícil injetar um script malicioso nessa URL. Por ventura, poderia ser um só uma mudança de background dizendo *Ha! Você foi hackeado*, ou um script que enviasse as informações para alguém.

### XSS Armazenado

É quando injetamos um código malicioso javascript que é armazenado no servidor do website. Normalmente feito através de inputs mal tratados Javascript que vão direto para o servidor. Também pode ser feito através da manipulação de requisições REST HTTP.

É um ataque crítico ao sistema, porque faz com que todos os usuários que acessem o recurso infectado acabem sendo expostos ao ataque.

Como exemplo, imagine um XSS aplicado em um input de comentário. Quando a barra de comentários for carregada para outro usuário, o script malicioso será carregado também.

### XSS DOM
