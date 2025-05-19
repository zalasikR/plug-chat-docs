---

id: webhook-message-status
title: Webhook - MessageStatus (Status da Mensagem)
---

## Método

#### Endpoint

`PUT` <https://app.plugchat.com.br/api/integrations/update-webhooks>

---

## Header

```https
Authorization: Bearer SEU_TOKEN_AQUI
Content-Type: application/json
```

\:::caution Atenção
O Plugchat não aceita webhooks que não sejam HTTPS.
\:::

---

## Conceituação

Esse webhook é acionado **quando o status de uma mensagem enviada é alterado** (por exemplo: enviada, entregue, lida). Ideal para sincronizar sistemas externos com o status atualizado de cada mensagem.

---

## Atributos

### Obrigatórios

| Atributo      | Tipo   | Descrição                         |
| ------------- | ------ | --------------------------------- |
| messageStatus | string | Webhook/EndPoint da sua aplicação |

### Opcionais

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
---

## Request Body

```json
{
  "value": {
    "messageStatus": "https://seuwebhook.com.br"
  }
}
```

---

## Response

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| status | string | Status da mensagem (SENT - se foi enviada, RECEIVED - se foi recebida, READ - se foi lida, READ-SELF - confirmação de leitura inativa, PLAYED - se foi ouvida ) |
| id | string | Identificador(es) da(s) mensagem(ns). |
| momment | integer | Momento em que a instância foi desconectada do número. |
| phoneDevice | integer | Indica o dispositivo que ocorreu o evento (0 - Celular)|
| phone | string | Número de telefone de destino da mensagem. |
| type  | string | Tipo do evento da instância, nesse caso será "MessageStatusCallback". |
| isGroup  | boolean | Indica se o chat é um grupo|

### 200 - Sucesso


```json
{
  "instanceId": "instance.id",
  "status": "SENT",
  "ids": ["999999999999999999999"],
  "momment": 1632234645000,
  "phoneDevice": 0,
  "phone": "5544999999999",
  "type": "MessageStatusCallback",
  "isGroup": false
}
{
  "instanceId": "instance.id",
  "status": "RECEIVED",
  "ids": ["999999999999999999999"],
  "momment": 1632234645000,
  "phoneDevice": 0,
  "phone": "5544999999999",
  "type": "MessageStatusCallback",
  "isGroup": false
}
{
  "instanceId": "instance.id",
  "status": "READ",
  "ids": ["999999999999999999999"],
  "momment": 1632234645000,
  "phoneDevice": 0,
  "phone": "5544999999999",
  "type": "MessageStatusCallback",
  "isGroup": false
}
{
  "instanceId": "instance.id",
  "status": "READ-SELF",
  "ids": ["999999999999999999999"],
  "momment": 1632234645000,
  "phoneDevice": 0,
  "phone": "5544999999999",
  "type": "MessageStatusCallback",
  "isGroup": false
}
{
  "instanceId": "instance.id",
  "status": "PLAYED",
  "ids": ["999999999999999999999"],
  "momment": 1632234645000,
  "phoneDevice": 0,
  "phone": "5544999999999",
  "type": "MessageStatusCallback",
  "isGroup": false
}
```

### 405 - Método não permitido

Verifique se o método da requisição é `PUT`, conforme especificado.

### 415 - Tipo de conteúdo inválido

Adicione no header da requisição o `Content-Type: application/json`.

---

## Observações

* Certifique-se de utilizar URLs seguras com HTTPS.
* O token de autenticação utilizado deve ser o **Authorization Token** fornecido pelo painel administrativo do plugchat