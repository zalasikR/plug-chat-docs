---
id: get-iswhatsapp
title: Número com Whatsapp ?
---

## Método

#### /phone-exists

`GET` https://www.plugchat.com.br/api/whatsapp/phone-exists

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

## Conceituação

Este método retorna se o número tem ou não Whatsapp.

:::important Importante

Plug não foi desenvolvido para dissiminação de spam para contatos que você não conhece, mesmo assim recomendamos que caso não tenha certeza que o número que vai enviar mensagens tenha Watsapp você pode e deve utilizar este método para certificar-se.

:::

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| phone | string | Telefone do destinatário no formato DDI DDD NUMERO Ex: 551199999999. **IMPORTANTE** Envie somente números, sem formatação ou máscara |

### Opcionais

| Atributos | Tipo | Descrição |
| :-------- | :--: | :-------- |
|           |      |           |

---

## Request Params

#### URL exemplo

Método

`GET` https://www.plugchat.com.br/api/whatsapp/phone-exists/5511999999999

---

## Response

### 200

| Atributos | Tipo | Descrição |
| :-- | :-- | :-- |
| exists | boolean | true para caso exista e false para casos onde o número não tenha Whatsapp |

Exemplo

```json
[
  {
    "exists": "true ou false"
  }
]
```

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/get-iswhatsapp.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
