---

id: webhook-message-delivery-error
title: Webhook - MessageDeliveryError (Erro de Entrega da Mensagem)
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

Esse webhook é acionado **quando ocorre um erro na entrega de uma mensagem enviada ao cliente**. Pode ser utilizado para registrar falhas de entrega e tomar ações automatizadas em sistemas externos.

---

## Atributos

### Obrigatórios

| Atributo             | Tipo   | Descrição                         |
| -------------------- | ------ | --------------------------------- |
| messageDeliveryError | string | Webhook/EndPoint da sua aplicação |

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
    "messageDeliveryError": "https://seuwebhook.com.br"
  }
}
```

---

## Response

### 200 - Sucesso

Webhook atualizado corretamente.

### 405 - Método não permitido

Verifique se o método da requisição é `PUT`, conforme especificado.

### 415 - Tipo de conteúdo inválido

Adicione no header da requisição o `Content-Type: application/json`.

---

## Observações

* Certifique-se de utilizar URLs seguras com HTTPS.
* O token de autenticação utilizado deve ser o **Authorization Token** fornecido pela equipe do Plugchat.