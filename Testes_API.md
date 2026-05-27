
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

## Testes em API REST e Métodos HTTP

Abaixo deixo os métodos HTTP mais usados de forma geral. Existem vários outros, não se limitando apenas aos exemplos abaixo:

### GET

Pegar ou pedir uma informação, onde o dado retornado pelo servidor é a representação do estado atual da informação solicitada naquele momento, podendo ser uma lista de informações, um único item ou um status code.


### POST

Pode ser entendido como postar/enviar informações para o servidor, podendo ser uma ação de criação de recursos ou, em casos mais complexos, enviar uma informação para obter um retorno específico.

### PUT

Atualizar informações de um recurso. É importante saber que, ao usar o PUT, deve-se usar todo o corpo da requisição (os mesmos campos que se recebe em um GET). Caso isso não seja feito, os demais campos serão entendidos como NULL; ou seja, mesmo que uma atualização seja feita em um campo do recurso, é necessário inserir todos os outros do corpo da requisição.

### PATCH

Mesmo funcionamento do PUT, porém, enquanto no PUT você deve passar todo o corpo da requisição para atualizar um recurso, no PATCH você pode passar apenas campos parciais, como, por exemplo, apenas o campo que você quer atualizar do recurso. Inclusive, eu tenho preferência por usar o PATCH.

### DELETE

Retirar/apagar um recurso que existe no servidor; por exemplo, você pode querer apagar o recurso passando um ID como parte do parâmetro na URL.

### CONNECT

Em casos específicos, pode ser usado para criar uma espécie de túnel entre o cliente e o servidor para troca de dados. Isso pode ser útil quando se quer testar algo ou obter uma resposta específica de um servidor, sem passar por servidores de cache, load balancers e outras soluções que ficam no meio entre o cliente e o servidor.
