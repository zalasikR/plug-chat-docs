---
id: update-webhooks
title: Atualizar webhooks
---

## Método

#### `PUT` update-webhooks

## Conceituação

Esse método atualiza os webhooks configurados na empresa

:::caution Atenção

O Plug não aceita webhooks que não sejam HTTPS

:::

---

### API

#### /update-webhooks

`PUT` https://www.plugchat.com.br/api/integrations/update-webhooks

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

#### Request Body

#### Body

```json
{
  "finishAttendance": "https://seuwebhook.com.br"
}
```

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| finishAttendance | string | URL do webhook a ser chamado quando um atendimento for finalizado. |

---

## Response

### 200

### Retorno do webhook quando finalizar um atendimento

```json
{
  "attendance": {
    "attendanceNumber": 1492,
    "customer": {
      "name": "nome",
      "phone": "554499999999"
    },
    "endTime": 1651065481865,
    "finishBy": "id do operador",
    "id": "id do atendimento",
    "operators": {
      "ID_DO_OPERADOR": true
    },
    "requestTime": 1651065472000,
    "startTime": 1651065471166,
    "status": "FINISH"
  },
  "chat": {
    "ID_DA_MENSAGEM": {
      "broadcast": false,
      "chatName": "nome",
      "forwarded": false,
      "fromMe": false,
      "instanceId": "instance id",
      "isGroup": false,
      "messageId": "ID_DA_MENSAGEM",
      "momment": 1651065478000,
      "phone": "554499999999",
      "photo": "URL_DA_FOTO",
      "senderName": "nome",
      "status": "RECEIVED",
      "text": {
        "message": "mensagem enviada"
      },
      "type": "ReceivedCallback",
      "waitingMessage": false
    },
    "ID_DA_MENSAGEM": {
      "fromMe": true,
      "isAutomaticMessage": true,
      "messageId": "ID_DA_MENSAGEM",
      "momment": 1651065479380,
      "phone": "554499999999",
      "status": "READ",
      "text": {
        "message": "só um momento"
      }
    }
  }
}
```

### 401

Neste caso certifique que esteja mandando o Authorization na header, se o token é válido e mandando o objeto com o webhook corretamente.

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---
