---
id: delete-message
title: Deletar mensagens
---

## Método

#### /messages

`DELETE` https://app.plugchat.com.br/api/whatsapp/messages

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

---

## Conceituação

Método utilizado para apagar uma mensagem em um chat, você pode deletar tanto uma mensagem que enviou quanto uma mensagen enviada por um contato, para utilizar este recurso você só vai precisar do messageId da mensagem que quer apagar.

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| messageId | string | id original da mensagem, no caso de mensagem enviada por você é o código que vem no seu reponse, caso seja uma mensagem enviada por um contato você vai receber este messageId pelo seu webhook de receive |
| phone | string | Telefone (ou ID do grupo para casos de envio para grupos) do destinatário/remetente no formato DDI DDD NUMERO Ex: 551199999999. **IMPORTANTE** Envie somente números, sem formatação ou máscara |
| owner | boolean | Informe true caso você tenha enviado a mensagem ou false para casos onde seja uma mensagem recebida |

### Opcionais

| Atributos | Tipo | Descrição |
| :-------- | :--: | :-------- |
|           |      |           |

---

## Request Params

#### URL exemplo

Método

`DELETE`

https://www.plugchat.com.br/api/whatsapp/messages?messageId=123&phone=5511999998888&owner=true

---

## Response

### 204

No content

| Atributos | Tipo | Descrição |
| :-------- | :--- | :-------- |
|           |      |           |

Exemplo

```json
{}
```

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/delete-message.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
