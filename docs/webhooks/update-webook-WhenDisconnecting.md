---

id: update-webhook-disconnected
title: Webhook - WhenDisconnecting (Desconectar)
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

Esse webhook é acionado **quando a sessão com o WhatsApp é desconectada**. É útil para registrar eventos de desconexão e tomar ações como notificações ou tentativas de reconexão.

---

## Atributos

### Obrigatórios

| Atributo          | Tipo   | Descrição                         |
| ----------------- | ------ | --------------------------------- |
| whenDisconnecting | string | Webhook/EndPoint da sua aplicação |

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
    "whenDisconnecting": "https://seuwebhook.com.br"
  }
}
```

---

## Response

### 200 - Sucesso

```json
{
  "momment": 1580163342,
  "error": "Device has been disconnected",
  "disconnected": true,
  "type": "DisconnectedCallback",
  "instanceId": "instance.id"
}

### 405 - Método não permitido

Verifique se o método da requisição é `PUT`, conforme especificado.

### 415 - Tipo de conteúdo inválido

Adicione no header da requisição o `Content-Type: application/json`.

---

## Observações

* Certifique-se de utilizar URLs seguras com HTTPS.
* O token de autenticação utilizado deve ser o **Authorization Token** fornecido pelo painel administrativo do plugchat