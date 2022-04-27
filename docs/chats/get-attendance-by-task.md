---
id: get-attendance-by-task
title: Pegar atendimento pela task
---

## Método

#### /get-attendance-by-task

`GET` https://www.plugchat.com.br/api/integrations/get-attendence-by-task

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

---

## Conceituação

Este método é reponsavel por retornar o atendimento pelo número da task

---

## Atributos

### Obrigatórios

| Atributos |  Tipo  | Descrição                                          |
| :-------- | :----: | :------------------------------------------------- |
| ticket:   | number | número do ticket gerado ao finalizar o atendimento |

### Opcionais

| Atributos | Tipo | Descrição |
| :-------- | :--: | :-------- |
|           |      |           |

---

## Request Params

#### URL exemplo

Método

`GET` https://www.plugchat.com.br/api/integrations/get-attendence-by-task

---

## Response

Exemplo

```json
{
  "attendanceData": {
    "ID_DO_ATENDIMENTO": {
      "attendanceNumber": 1473,
      "customer": {
        "name": "nome",
        "phone": "554499999999"
      },
      "endTime": 1650480054206,
      "finishBy": "ID_DO_OPERADOR",
      "id": "ID_DO_ATENDIMENTO",
      "operators": {
        "ID_DO_OPERADOR": true
      },
      "requestTime": 1650479220000,
      "startTime": 1650480001521,
      "status": "FINISH",
      "trelloTask": {
        "id": "ID_TRELLO_TASK",
        "idBoard": "ID_BOARD",
        "idList": "ID_LIST",
        "shortUrl": "URL_CURTA",
        "url": "URL_TRELLO"
      }
    }
  },
  "chat": {
    "ID_MENSAGEM": {
      "broadcast": false,
      "chatName": "nome",
      "forwarded": false,
      "fromMe": false,
      "instanceId": "ID_INSTANCE",
      "isGroup": true,
      "messageId": "ID_MENSAGEM",
      "momment": 1650479278000,
      "participantPhone": "554499999999",
      "phone": "554499999999",
      "photo": "URL_FOTO",
      "senderName": "nome",
      "senderPhoto": "URL_FOTO",
      "status": "READ",
      "text": {
        "message": "texto da mensagem"
      },
      "type": "ReceivedCallback",
      "waitingMessage": false
    }
  }
}
```

### 401

Neste caso certifique que esteja informando o Authorization da headers corretamente e se o token é válido.

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

### 500

Neste caso certifique que esteja enviando um número válido no atributo ticket.

---
