---
id: send-text-status
title: Enviando texto status
---

## Método

#### /send-text-status

`POST` https://www.plugchat.com.br/api/whatsapp/send-text-status

## Header
#### Toda requisição http feita precisa passar sua header de autorização.


| Key            | Value                   |
| :------------: |   :---------------:     |
| Authorization: |   1nEFbU3EktLnV7LIIzX   |

---

## Conceituação

Você pode postar textos no seu status e este método é responsável  por isso, lembre-se que os status somem após 24 horas.

---

## Atributos

### Obrigatórios

| Atributos |  Tipo  | Descrição                              |
| :-------- | :----: | :------------------------------------- |
| message   | String | Mensagem a ser enviada para seu status |

---

### Opcionais

| Atributos | Tipo | Descrição |
| :-------- | :--: | :-------- |
|           |      |           |

---

## Request Body

#### URL

Método

`POST` https://www.plugchat.com.br/api/whatsapp/send-text-status

#### Body

```json
{
  "message": "Sua mensagem para status"
}
```

---

## Response

### 200

| Atributos | Tipo   | Descrição      |
| :-------- | :----- | :------------- |
| zaapId    | string | id no Plug     |
| messageId | string | id no whatsapp |

Exemplo

```json
{
  "zaapId": "3999984263738042930CD6ECDE9VDWSA",
  "messageId": "D241XXXX732339502B68"
}
```

### 405

Neste caso certifique-se que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique-se de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/send-text-status.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
