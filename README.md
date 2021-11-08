# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento das API's nos Capstones do Q2.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

### Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

### Animals

O usuário deve possuir recursos, autenticação, para escrever. Todos podem ler.
O endpoint /animals/ é composto pelos campos: "type", "name" e "userId".
Authorization Bearer {{token}}

Exemplo:
POST:
{
"type": "gato",
"name": "Sol",
"userId": 2
}

GET:
[
{
"type": "gato",
"name": "Sol",
"userId": 2,
"id": 1
}
]

### My Favorite Animals

O usuário deve possuir recursos, autenticação, para escrever e deve está logado para leitura.
O endpoint /myFavoriteAnimals/ é composto pelos campos: "gatos", "cachorros", "pato", "ornintorrinco", todos eles sendo true ou false. Há, também, o campo "userId", que leva o id do usuário. Deve ter um Authorization Bearer {{token}}

Exemplo:
POST:
{
"gatos": true,
"cachorros": true,
"pato": false,
"ornitorrinco": false,
"userId": 2,
}

GET:
[
{
"gatos": true,
"cachorros": true,
"pato": false,
"ornitorrinco": false,
"userId": 2,
"id": 1
}
]
