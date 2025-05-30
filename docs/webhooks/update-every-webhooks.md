---
id: update-every-webhooks
title: Atualizar todos webhooks
---

## Conceituação

Esse endpoint serve para você que deseja alterar todos os webhooks para a mesma URL de uma só vez.

:::caution Atenção

O Z-API não aceita webhooks que não sejam HTTPS

:::

---

## Atualizando Webhooks

### API

#### /update-every-webhooks

`PUT` <https://app.plugchat.com.br/api/integrations/update-webhooks>

### Header

|      Key       |            Value            |
| :------------: |     :-----------------:     |
| Authorization  |     1nEFbU3EktLnV7LIIzX |
---

### Request Body

#### Obrigatórios

| Atributos |  Tipo  | Descrição                      |
| :-------- | :----: | :----------------------------- |
| value      | string | Endpoint do webhook |

#### Opcionais

| Atributos               |  Tipo  | Descrição                      |
| :--------               | :----: | :----------------------------- |
| notifySentByMe | boolean | Ativar webhook de mensagens recebidas e enviadas por mim |

```json
{
  "value": "https://endereco-do-seu-sistema.com.br/instancia/SUA_INSTANCIA/status",
  "notifySentByMe": true
}
```

---

## Retorno do endpoint

### 200

```json
{
  "value": boolean
}
```