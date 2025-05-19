---
id: archive-chat
title: Arquivar chats
---

## Método

#### /modify-chat

`POST` https://app.plugchat.com.br/api/whatsapp/modify-chat

## Header

#### Toda requisição HTTPS precisa passar seu token de autorização no header.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

---

## Conceituação

Este método é responsável por arquivar e desarquivar seus chats.

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| phone | integer | Número de telefone que você deseja alterar no **SEU** chat |
| action | string | Atributo para arquivar e desarquivar o chat |

---

## Request Body

Exemplo

```json
{
"phone": "5544999999999",
"action": "archive" ou "unarchive"
}
```

---

## Response

### 200

| Atributos | Tipo    | Descrição                       |
| :-------- | :------ | :------------------------------ |
| value     | boolean | Atributo de confirmação da ação |

Exemplo

```json
{
  "value": true
}
```

### 405

Neste caso certifique-se que esteja enviando corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no início deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/archive-chat.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
