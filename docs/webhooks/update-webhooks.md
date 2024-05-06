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
  "finishAttendance": "https://seuwebhook.com.br",
  "startAttendance": "https://seuwebhook.com.br",
  "receiveMessage": "https://seuwebhook.com.br",
  "sendingMessage": "https://seuwebhook.com.br",
  "messageDeliveryError": "https://seuwebhook.com.br",
  "messageStatus": "https://seuwebhook.com.br",
  "whenDisconnecting": "https://seuwebhook.com.br"
}
```

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| finishAttendance | string | URL do webhook a ser chamado quando um atendimento for finalizado. |
| startAttendance | string | URL do webhook a ser chamado quando um atendimento for Iniciado. |
| receiveMessage | string | URL do webhook a ser chamado quando receber uma mensagem. |
| sendingMessage | string | URL do webhook a ser chamado quando enviar uma mensagem. |
| messageDeliveryError | string | URL do webhook a ser chamado quando houver um erro na entrega da mensagem. |
| messageStatus | string | URL do webhook a ser chamado quando o status da mensagem for atualizado. |
| whenDisconnecting | string | URL do webhook a ser chamado ao se desconectar. |

---

## Response

### 200

### Retorno do webhook quando finalizar um atendimento

#### Ao Finalizar Atendimento

**Nova configuração** <br/> No painel do dashboard, em `configurações > categorias de atendimento` incluímos a opção de cadastrar uma lista de categorias e vincular itens para cada uma. Com essa mudança o webhook terá um novo retorno, mas apenas nessa parte.

O que mudou?<br/> Nada, `attendanceCategory` continuará funcionando como antes **(exemplo-1)** e `attendanceCategories` é uma nova implementação que retorna uma lista **(exemplo-2)** com base no que foi categorizado ao finalizar o atendimento.

Importante notar que ambos retornos funcionarão, então com base no que foi configurado nas categorias será então retornado, sendo totalmente dinâmico.

**Exemplo-1**

```json
{
  "attendance": {
    "attendanceCategory": {
      "color": "#DDDD",
      "id": "id da categoria",
      "name": "nome da categoria"
    },
    "attendanceNumber": 1492,
    "customer": {
      "name": "nome",
      "phone": "554499999999"
    },
    "departament": "Nome do departamento",
    "endTime": 1651065481865,
    "finishBy": "Nome do operador",
    "operatorReport ": "Relato do operador",
    "ratingObservation": "Observação do cliente",
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

<br/>

**Exemplo-2**

```json
{
  "attendance": {
    "attendanceCategories": [
      {
        "categoryId": "id_categoria",
        "categoryName": "Padrão",
        "color": "cor_categoria",
        "itemId": "id_item_vinculado_na_categoria",
        "itemName": "Nome do item"
      },
      {
        "categoryId": "id_categoria",
        "categoryName": "nome_categoria",
        "color": "cor_categoria",
        "itemId": "id_item_vinculado_na_categoria",
        "itemName": "Nome do item"
      }
    ],
    "attendanceNumber": 1492,
    "customer": {
      "name": "nome",
      "phone": "554499999999"
    },
    "departament": "Nome do departamento",
    "endTime": 1651065481865,
    "finishBy": "Nome do operador",
    "operatorReport ": "Relato do operador",
    "ratingObservation": "Observação do cliente",
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

#### Ao Iniciar Atendimento

```json
{
  "attendance": {
    "attendanceNumber": 1492,
    "customer": {
      "name": "nome",
      "phone": "554499999999"
    },
    "departament": "Nome do departamento",
    "operator": "Nome do operador",
    "momment": 1651065472000,
    "startTime": 1651065471166,
    "status": "PROGRESS"
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

---

### 401

Neste caso certifique que esteja mandando o Authorization na header, se o token é válido e mandando o objeto com o webhook corretamente.

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---
