---

id: webhook-receive-message
title: Webhook - ReceiveMessage (Mensagem Recebida)
---
### Método

#### Endpoint

`PUT` <https://app.plugchat.com.br/api/integrations/update-webhoo>

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

Esse webhook é acionado **quando uma mensagem é recebida de um cliente** na plataforma Plugchat. Ele é útil para registrar ou reagir a mensagens recebidas em tempo real por sistemas externos.

---

## Atributos

### Obrigatórios

| Atributo       | Tipo   | Descrição                         |
| -------------- | ------ | --------------------------------- |
| receiveMessage | string | Webhook/EndPoint da sua aplicação |

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
    "receiveMessage": "https://seuwebhook.com.br"
  }
}
```

---

## Response

### 200 - Sucesso

```json
{
  "isStatusReply": false,
  "senderLid": "81896604192873@lid",
  "connectedPhone": "554499999999",
  "waitingMessage": false,
  "isEdit": false,
  "isGroup": false,
  "isNewsletter": false,
  "instanceId": "A20DA9C0183A2D35A260F53F5D2B9244",
  "messageId": "A20DA9C0183A2D35A260F53F5D2B9244",
  "phone": "5544999999999",
  "fromMe": false,
  "momment": 1632228638000,
  "status": "RECEIVED",
  "chatName": "name",
  "senderPhoto": "https://",
  "senderName": "name",
  "participantPhone": null,
  "participantLid": null,
  "photo": "https://",
  "broadcast": false,
  "type": "ReceivedCallback",
  "text": {
    "message": "teste",
    "descritpion": "(opcional) em caso da mensagem possuir uma descrição inserida pelo WhatsApp",
    "title": "(opcional) em caso da mensagem possuir um título inserido pelo WhatsApp",
    "url": "(opcional) caso a mensagem possua um link ligado a ela. Exemplo: mensagem de catálogo possui um botão 'Ver catálogo'",
    "thumbnailUrl": "(opcional) caso a mensagem possua uma imagem de thumbnail ligada a ela. Exemplo: mensagem de convite de grupo possui a imagem do grupo"
  }
}
---

### 405 - Método não permitido

Verifique se o método da requisição é `PUT`, conforme especificado.

### 415 - Tipo de conteúdo inválido

Adicione no header da requisição o `Content-Type: application/json`.

---

## Observações

* Certifique-se de utilizar URLs seguras com HTTPS.
* O token de autenticação utilizado deve ser o **Authorization Token** fornecido pelo painel administrador do Plugchat.
