
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

<img width="907" height="593" alt="image" src="https://github.com/user-attachments/assets/af2c8f33-5f80-4ecf-833d-26a14a7363d7" />


### POST

Pode ser entendido como postar/enviar informações para o servidor, podendo ser uma ação de criação de recursos ou, em casos mais complexos, enviar uma informação para obter um retorno específico.

<img width="909" height="578" alt="image" src="https://github.com/user-attachments/assets/d5488122-9f1a-4319-b798-df18e8ae8163" />

### PUT

Atualizar informações de um recurso. É importante saber que, ao usar o PUT, deve-se usar todo o corpo da requisição (os mesmos campos que se recebe em um GET). Caso isso não seja feito, os demais campos serão entendidos como NULL; ou seja, mesmo que uma atualização seja feita em um campo do recurso, é necessário inserir todos os outros do corpo da requisição.

<img width="910" height="585" alt="image" src="https://github.com/user-attachments/assets/5e635df3-df21-48ae-85d5-21b682ca8c54" />


### PATCH

Mesmo funcionamento do PUT, porém, enquanto no PUT você deve passar todo o corpo da requisição para atualizar um recurso, no PATCH você pode passar apenas campos parciais, como, por exemplo, apenas o campo que você quer atualizar do recurso. Inclusive, eu tenho preferência por usar o PATCH.

<img width="915" height="586" alt="image" src="https://github.com/user-attachments/assets/88d9cc74-cfa8-46d9-8770-f30e1eef6e18" />

### DELETE

Retirar/apagar um recurso que existe no servidor; por exemplo, você pode querer apagar o recurso passando um ID como parte do parâmetro na URL.

<img width="917" height="584" alt="image" src="https://github.com/user-attachments/assets/b409bec8-f0bb-4e53-bfef-0e7dfb220a16" />

### CONNECT

Em casos específicos, pode ser usado para criar uma espécie de túnel entre o cliente e o servidor para troca de dados. Isso pode ser útil quando se quer testar algo ou obter uma resposta específica de um servidor, sem passar por servidores de cache, load balancers e outras soluções que ficam no meio entre o cliente e o servidor.

<img width="905" height="582" alt="image" src="https://github.com/user-attachments/assets/e5313d9d-a782-4c6b-8f5c-9f26ff9f31fe" />

### Status Codes HTTP

| Código | Descrição |
| :--- | :--- |
| **200 OK** | Retornado quando tudo funcionou conforme o esperado. Comum em requisições GET. |
| **201 Created** | Indica que um novo recurso foi criado com sucesso, geralmente após uma requisição POST. |
| **204 No Content** | A requisição foi efetuada, mas não há nada para enviar de volta no corpo da resposta. |
| **400 Bad Request** | Algo estava errado com a requisição, geralmente um erro de sintaxe ou entrada inválida. |
| **401 Unauthorized** | Acesso negado porque as credenciais de autenticação estão faltando ou incorretas. |
| **404 Not Found** | Retornado quando o recurso ou endpoint solicitado não existe/não encontrado. |
| **500 Internal Server Error** | Um erro genérico que significa que o servidor encontrou um problema que não sabia como lidar/resolver. |

