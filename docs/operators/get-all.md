---
id: get-all
title: Pegar dados dos operadores
---

## Método

#### /get-all

`GET` https://www.plugchat.com.br/api/operator/get-all

## Header

#### Para buscar os dados dos operadores, o Ticket precisa ser passado na Header.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |
|    Ticket:     |        0000         |

---

## Conceituação

Este método é reponsável por retornar os dados dos operadores

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-------- | :--- | :-------- |
|           |      |           |

### Opcionais

| Atributos | Tipo | Descrição |
| :-------- | :--: | :-------- |
|           |      |           |

---

## Request Params

#### URL exemplo

Método

`GET` https://www.plugchat.com.br/api/operator/get-all

---

## Response

### 200

---

| Atributos    |     Tipo     | Descrição                                   |
| :----------- | :----------: | :------------------------------------------ |
| createdAt    |    number    | Timestamp da criação do operador            |
| departaments | array string | Array com ids dos departamentos do operador |
| name         |    string    | Nome do operador                            |
| active       |   boolean    | Se o operador está ativo ou não             |
| id           |    string    | Id do operador                              |
| login        |    string    | Login do operador                           |

Objeto Exactsales

| Atributos | Tipo         | Descrição                       |
| :-------- | :----------- | :------------------------------ |
| lastName  | string       | Sobrenome do Operador           |
| phone     | number       | Fone do operador 1              |
| phone2    | number       | Fone do operador 2              |
| name      | string       | Nome do operador                |
| active    | boolean      | Se o operador está ativo ou não |
| groupList | array string | Lista de grupos do operador     |
| id        | string       | ID do operador                  |
| email     | string       | E-mail do operador              |

Exemplo

```json
{
        "createdAt": 1617805323000,
        "departaments": [
            "4d8f72e1-3b4a-4d95-8ce7-1b5490063c3d"
        ],
        "name": "nome",
        "active": true,
        "id": "ID_DO_OPERADOR",
        "login": "teste"
    },
    {
        "createdAt": 1617805323000,
        "departaments": [
            "4d8f72e1-3b4a-4d95-8ce7-1b5490063c3d"
        ],
        "name": "nome",
        "active": true,
        "id": "ID_DO_OPERADOR",
        "login": "teste"
    },
    {
        "active": true,
        "login": "este",
        "createdAt": 1617805323000,
        "name": "nome",
        "id": "ID_DO_OPERADOR",
        "exactsales": {
            "lastName": "TESTE",
            "phone": null,
            "phone2": null,
            "name": "TESTE",
            "active": true,
            "groupList": [],
            "id": 9128735,
            "email": "teste@.com.br"
        },
        "departaments": [
            "4d8f72e1-3b4a-4d95-8ce7-1b5490063c3d",
            "8aeb3d4e-6c2f-47e2-a0f5-d0f5d6d0fb2f",
            "7395a4f8-85a9-4a68-9103-6f35231a6f96",
            "b6c1e7da-6d3e-4ccf-8c33-9e7f1f5dd212"
        ]
    },
```

### 401

Neste caso certifique que esteja informando o Authorization da headers corretamente e se o token é válido.

### 405

Neste caso certifique que esteja enviando corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no início deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

### 500

Neste caso certifique que esteja enviando um número válido no atributo ticket.

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/get-all-operators.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
