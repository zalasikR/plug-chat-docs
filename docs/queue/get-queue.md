---
id: get-queue
title: Fila
---

## Método

#### /queue

`GET` https://app.plugchat.com.br/api/whatsapp/queue

## Header
#### Toda requisição http feita precisa passar sua header de autorização.


| Key            | Value                   |
| :------------: |   :---------------:     |
| Authorization: |   1nEFbU3EktLnV7LIIzX   |

## Conceituação

Este método é responsável por retornar todas mensagens que estão em sua fila aguardando para ser processada.

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-------- | :--: | :-------- |
|           |      |           |

### Opcionais

| Atributos | Tipo | Descrição |
| :-------- | :--: | :-------- |
|           |      |           |

---

## Request Params

#### URL exemplo

Método

`GET` https://www.plugchat.com.br/api/whatsapp/queue

---

## Response

### 200

| Atributos | Tipo         | Descrição                       |
| :-------- | :----------- | :------------------------------ |
| size      | string       | Numero de mensagens na fila     |
| messages  | array string | Array com as menssagens da fila |

Array Messages

| Atributos | Tipo     | Descrição                   |
| :-------- | :------- | :-------------------------- |
| size      | string   | Numero de mensagens na fila |
| Message   | string   | Texto da Mensagem           |
| Phone     | string   | Fone do destinatário        |
| ZaapId    | string   | ID da mensagem no Plug      |
| Created   | timetamp | Data da mensagem            |
| MessageId | string   | ID da mensagem              |

Exemplo

```json
{
  "size": 2,
  "messages": [
    {
      "Message": "Mensagem da fila 1",
      "Phone": "5511999999999",
      "ZaapId": "39BB1684570F00E91090F6BBC7EE7646",
      "Created": 1624977905648,
      "MessageId": "7AD29EAA5EF34C301F0B"
    },
    {
      "Message": "Mensagem da fila 2",
      "Phone": "5511999999999",
      "ZaapId": "39BB1685172AB008542A7E0B862A54DF",
      "Created": 1624977906907,
      "MessageId": "517AEF0FDE834DADJJFC8"
    }
  ]
}
```

### 405

Neste caso certifique-se que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/get-queue.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
