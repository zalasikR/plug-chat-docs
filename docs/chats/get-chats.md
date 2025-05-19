---
id: get-chats
title: Pegar chats
---

## Método

#### /chats

`GET` https://app.plugchat.com.br/api/whatsapp/chats

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

---

## Conceituação

Este método é responsável por retornar todos os chats.

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| page | integer | Utilizado para paginação você deve informar aqui a página de chats que quer buscar |
| pageSize | integer | Especifica o tamanho do retorno de chats por página |

---

## Request Params

#### URL exemplo

Método

`GET` https://www.plugchat.com.br/api/whatsapp/chats

---

## Response

### 200

| Atributos | Tipo | Descrição |
| :-- | :-- | :-- |
| name | string | **Nome ** atribuído ao chat, lembrando que se for um grupo ou lista de transmissão deve retornar os respectivos IDs |
| phone | string | Phone do contato |
| unread | string | indica o número de mensagens não lidas em um chat |
| lastMessageTime | string | Timestamp com a data e hora da última interação com o chat |
| isMuted | string | 0 ou 1 indica se você silenciou ou não este chat |
| isMarkedSpam | boolean | true ou false indica se você marcou este chat como spam |
| profileThumbnail | string | URL da foto do chat **o Whatsapp apaga após 48hs** |
| messagesUnread | integer | **descontinuado** |

Exemplo

```json
[
  {
    "name": "Plug-suporte",
    "phone": "5511999999999",
    "unread": "0",
    "lastMessageTime": "1622991687",
    "isMuted": "0",
    "isMarkedSpam": "false",
    "profileThumbnail": null,
    "messagesUnread": 0
  },
  {
    "name": "Plug-Team",
    "phone": "5511999999999",
    "unread": "0",
    "lastMessageTime": "1622990503",
    "isMuted": "0",
    "isMarkedSpam": "false",
    "profileThumbnail": "https://pps.whatsapp.net/v/t61.24694-24/170931400_212202650511993_3423338295209291992_n.jpg?ccb=11-4&oh=4b96b3bf7114122667f80d021b194f2c&oe=60C179E2",
    "messagesUnread": 0
  }
]
```

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no início deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/get-chats.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
