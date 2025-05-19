---
id: get-all-departaments
title: Pegar todos os departamentos
---

## Método

#### /departaments

`GET` https://app.plugchat.com.br/api/integrations/departments

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

---

## Conceituação

Este método é responsável por retornar os departamentos cadastrados na sua conta.

---

## Request Params

#### URL exemplo

Método

`GET` https://www.plugchat.com.br/api/integrations/departments

---

## Response

### 200

| Atributos | Tipo    | Descrição                            |
| :-------- | :------ | :----------------------------------- |
| active    | boolean | Se o departamento está ativo ou não  |
| id        | string  | identificador do departamento        |
| name      | string  | Nome do departamento                 |
| createdAt | number  | timestamp da criação do departamento |

Exemplo

```json
[
  {
    "active": true,
    "id": "ID_DO_DEPARTAMENTO",
    "name": "Nome",
    "createdAt": 1617708992443
  }
]
```

### 401

Neste caso certifique-se que esteja enviando o corretamente o Authorization na headers e se o mesmo é um token válido.

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---
