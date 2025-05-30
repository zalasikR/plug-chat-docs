---
id: get-contacts
title: Pegar contatos
---

## Método

#### /contacts

`GET` https://app.plugchat.com.br/api/whatsapp/contacts

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

---

## Conceituação

Este método é reponsável por retornar todos os contatos do Whatsapp. Lembre-se do que foi dito na introdução sobre número de contatos, caso tenho pulado esta parte, sugiro que você volte um passo e leia a nossa introdução sobre contatos.

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| page | integer | Utilizado para paginação você deve informar aqui a página de contatos que quer buscar |
| pageSize | integer | Especifica o tamanho do retorno de contatos por página |

### Opcionais

| Atributos | Tipo | Descrição |
| :-------- | :--: | :-------- |
|           |      |           |

---

## Request Params

#### URL exemplo

Método

`GET` https://www.plugchat.com.br/api/whatsapp/contacts?page=1&pageSize=20

---

## Response

### 200

| Atributos | Tipo | Descrição |
| :-- | :-- | :-- |
| phone | string | Phone do contato |
| name | string | **Nome e sobrenome** do contato, só vai retornar preenchido caso você tenha o número em seus contatos |
| short | string | **Nome** do contato, só vai retornar preenchido caso você tenha o número em seus contatos |
| vname | string | Nome do contato caso você tenha ele como contato |
| notify | string | Nome informado nas configurações de nome do Whatsapp |

Exemplo

```json
[
  {
    "name": "Nome e sobrenome do contato 1",
    "short": "Nome do contato 1",
    "notify": "Nome no Whatsapp 1",
    "vname": "Nome no vcard",
    "phone": "559999999999"
  }
]
```

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no início deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/get-contacts.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
