
# API REST

## Meu entendimento sobre API

API é uma interface de programação de aplicativos, através dela é definido como aplicativos ou dispositivos podem se comunicar entre si.

##  Sobre API REST

A API REST (Transferência de Estado Representacional) é um tipo de arquitetura que utiliza métodos de requisição HTTP para acessar e manipular dados pela internet.

REST é uma forma padronizada de estruturar uma API para que ela seja intuitiva e fácil de usar, sendo uma estrutura vital para serviços/aplicações web.

## Conceitos

### Recursos (Resources) e URIs

No REST, tudo é um recurso que precisa ter um endereço rastreável as URIs (Uniform Resource Identifier), Exemplo: https://api.loja.com/produtos/123 (O recurso aqui é o produto de ID 123).

### Interface Uniforme (Uniform Interface)

Diz respeito ao padrão utilizado ao acessar e manipular todos os recursos, no lugar de ter que ter uma url para deletar ou atualizar um item, é sempre utilizada a mesma URI, alterando apenas o método de chamada daquele recurso com métodos HTTP (GET, POST, PUT, DELETE).

### Representações (Representations/Cacheability)

Quando existe uma solicitação Client-Server ou vice versa, o que é devolvido no momento é a representação do estado que aquele recurso está naquele momento, utilizando o exemplo acima, seria como se a resposta do servidor nos devolvesse exatamente a representação de como o GET https://api.loja.com/produtos/123, produto 123 está nesse exato momento no Banco de dados, as respostas possuem caches para melhorar o desempenho e reduzir o tempo de processamento em consultas repetitivas a informações no servidor.

### Sem Estado (Statelessness)

Esse conceito é sobre que nenhum dado é salvo sobre as sessões anteriores, nem sobre o estado do cliente e dados da sessão, onde cada requisição é independente e contém todos os dados necessários para consultas, exemplo GET https://api.loja.com/produtos/123.

Por isso que em testes onde precisa de Auth, todas as requisições precisam ser enviadas com a chave da api ou token de Autenticação.

## Porque testar uma API?

### Testar Mais Cedo

Quanto mais cedo um bug for encontrado, mais barato e rápido é corrigi-lo!

### Facilidade de validação das Regras de Negócio.

Fica mais fácil validar se a lógica de negócio está de acordo.

### Rapidez e Eficiência

Testar apenas no front-end pode demandar tempo, pois a automação pode precisar clicar em CAPTCHA e enfrentar maiores dificuldades para notar problemas de regras de negócios e lógicas.

### Maior Estabilidade

Digamos que no front-end existem muitas mudanças de classes, alteração de botões, etc.
Uma vez com todos os testes em API realizados e bugs devidamente corrigidos, garantimos que qualquer problema no front-end não se trata de problemas na aplicação, pois já foi validado previamente, garantindo estabilidade e rastreabilidade na possível correção.

### Maior Cobertura

Em um mundo onde existem diversas aplicações (Web, Mobile, etc.), se garantirmos que a API está 100% funcional de acordo com os requisitos, garantimos qualidade em toda e qualquer plataforma.
