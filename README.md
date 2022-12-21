# Readme do Projeto JSON Server

Essa é a documentação da FakeAPI desenvolvida para fazer testes com a lib FakeAPI. Não devo me aprofundar muito nesta lib, pois o que vamos aprender no M4 é diferente do que acontece com essa lib.

## Endpoints

Existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### Cadastro

POST /register

Este é o endpoint para fazer a requisição de registro.
Os Campos email e password são obrigatórios.

==============================
Exemplo de requisição do usuário:
{
    "email": "zxcd@mail.com",
    "password": 123456
}
===============================
==============================
Exemplo de Resposta da API:
{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Inp4Y2RAbWFpbC5jb20iLCJpYXQiOjE2NzE2MzUyNzIsImV4cCI6MTY3MTYzODg3Miwic3ViIjoiMyJ9.S6XpMubmbqdHWgIsaMVxR2n0mwoIYE3nGk5m25hsKNQ",
"user": {
"email": "zxcd@mail.com",
"id": 3
}
}
===============================

### Login

POST /login

Este é o endpoint para fazer a requisição de login.
Os Campos email e password são obrigatórios.

==============================
Exemplo de requisição do usuário:
{
    "email": "zxcd@mail.com",
    "password": 123456
}
===============================
==============================
Exemplo de Resposta da API:
{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Inp4Y2RAbWFpbC5jb20iLCJpYXQiOjE2NzE2MzUzNTUsImV4cCI6MTY3MTYzODk1NSwic3ViIjoiMyJ9.f0xHBK1VWGP2Ddt425uL8wJAhohHiNiZe3QZ4JErqOc",
"user": {
"email": "zxcd@mail.com",
"id": 3
}
}
===============================

### Get Games

GET /games

Endpoint para listar todos os games cadastrados.

### Get Animals

GET /animals

Endpoint para listar todos os animais cadastrados.


## Endpoints Protegidas

### Get Users

GET /users/${userID}

Endpoint para listar informações do usuário.
É necessário passar o id do usuário, após o endpoint users
Apenas o titular da conta consegue fazer esta requisição através do accessToken.
===============================
headers: {
Authorization: `Bearer ${token}`
}
===============================
