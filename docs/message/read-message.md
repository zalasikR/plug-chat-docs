---
id: read-message
title: Ler mensagens
---

## Método

#### /read-message

`POST` https://www.plugchat.com.br/api/whatsapp/read-message

## Header

#### Toda requisição http precisa passar seu token de autorização no header

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

---

## Conceituação

Método utilizado para marcar uma mensagem em um chat como lida.

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| phone | string | Telefone (ou ID do grupo para casos de envio para grupos) do destinatário/remetente no formato DDI DDD NÚMERO. Ex: 551199999999. IMPORTANTE: Envie somente números, sem formatação ou máscara. |
| messageId | string | ID original da mensagem. No caso de mensagem enviada por você, é o código que vem no seu response; caso seja uma mensagem enviada por um contato, você receberá este messageId pelo seu webhook de received. |

### Opcionais

| Atributos | Tipo | Descrição |
| :-------- | :--: | :-------- |
|           |      |           |

---

## Request Body

```json
{
  "phone": "5511999998888",
  "messageId": "3999984263738042930CD6ECDE9VDWSA"
}
```

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

Neste caso, certifique-se de que está enviando corretamente a especificação do método. Verifique se você enviou o POST ou GET conforme especificado no início deste tópico.

### 415: 
Caso você receba um erro 415, adicione na header da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria, "application/json".

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/read-message.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
