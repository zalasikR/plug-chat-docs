---

id: webhook-sending-message
title: Webhook - SendingMessage (Envio de Mensagem)
---
## Método

#### Endpoint

`PUT` <https://app.plugchat.com.br/api/integrations/update-webhooks>

---

## Header

```http
Authorization: Bearer SEU_TOKEN_AQUI
Content-Type: application/json
```

\:::caution Atenção
O Plugchat não aceita webhooks que não sejam HTTPS.
\:::

---

## Conceituação

Esse webhook é acionado **quando uma mensagem é enviada para um cliente**. Permite registrar ou realizar ações sempre que sua equipe ou automações enviarem mensagens por meio da plataforma Plugchat.

---

## Atributos

### Obrigatórios

| Atributo       | Tipo   | Descrição                         |
| -------------- | ------ | --------------------------------- |
| sendingMessage | string | Webhook/EndPoint da sua aplicação |

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
    "sendingMessage": "https://seuwebhook.com.br"
  }
}
```

---

## Response

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| phone | string | Número de telefone de destino da mensagem. |
| zaapId | string | Identificador da mensagem na conversa. |
| type | string | Tipo do evento da instância, nesse caso será "DeliveryCallback". |

### 200 - Sucesso

```json
{
  "phone": "554499999999",
  "zaapId": "A20DA9C0183A2D35A260F53F5D2B9244",
  "messageId": "A20DA9C0183A2D35A260F53F5D2B9244",
  "type": "DeliveryCallback",
  "instanceId": "instance.id"
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


