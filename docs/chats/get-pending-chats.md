---
id: get-pending-chats
title: Pegar chats pendentes
---

## Método

#### /get-pending-chats

`GET` https://app.plugchat.com.br/api/chat/get-pending-chats

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

---

## Conceituação

Este método é responsável por retornar todos os chats pendentes.

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

`GET` https://www.plugchat.com.br/api/chat/get-pending-chats

---

## Response

### 200

| Atributos | Tipo | Descrição                                                                                                                            |
| :-- | :-- |:-------------------------------------------------------------------------------------------------------------------------------------|
| name | string | **Nome** atribuído ao chat. Para grupos ou listas de transmissão, retornará os respectivos IDs                                       |
| phone | string | Número de telefone do contato                                                                                                        |
| profileThumbnail | string | URL da imagem de miniatura do perfil associada ao contato ou grupo                                                                   |
| lastMessageTime | string | Data e hora da última interação com o chat, no formato de timestamp                                                                  |
| unreadMessagesCount | string | Quantidade de mensagens não lidas no chat.                                                                                           |                                                                                  |
| isMarkedAsUnread | string | Indica se o chat está marcado como não lido (true ou false)                                                                          |                                                                        |                                                                                  |
| isMuted | boolean | 	Indica se o chat está silenciado (true ou false)                                                                                    |                                                                          |


Exemplo

```json
[
  {
    "name": "Plug-suporte",
    "phone": "5511999999999",
    "profileThumbnail": null,
    "lastMessageTime": "1622991687",
    "unreadMessagesCount": 0,
    "isMarkedAsUnread": false,
    "isMuted": false
  },
  {
    "name": "Plug-Team",
    "phone": "5511999999999",
    "profileThumbnail": "https://pps.whatsapp.net/v/t61.24694-24/170931400_212202650511993_3423338295209291992_n.jpg?ccb=11-4&oh=4b96b3bf7114122667f80d021b194f2c&oe=60C179E2",
    "lastMessageTime": "1622990503",
    "unreadMessagesCount": 4,
    "isMarkedAsUnread": false,
    "isMuted": false
  }
]

```

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o GET conforme especificado no início deste tópico.

### 415

Se der erro 415, verifique se adicionou o "Content-Type" correto no header da requisição, como "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/develop/json-examples/get-pending-chats.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
