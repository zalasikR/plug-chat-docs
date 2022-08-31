---
id: send-image-status
title: Enviando imagem status
---

## Método

#### /send-image-status

`POST` https://www.plugchat.com.br/api/whatsapp/send-image-status

## Header
#### Toda requisição http feita precisa passar sua header de autorização.


| Key            | Value                   |
| :------------: |   :---------------:     |
| Authorization: |   1nEFbU3EktLnV7LIIzX   |

---

## Conceituação

Método responsavel por enviar uma imagem para seu status, lembre-se que os status somem após 24 horas.

---

## Atributos

### Obrigatórios

| Atributos |  Tipo  | Descrição                    |
| :-------- | :----: | :--------------------------- |
| image     | String | Link da imagem ou seu Base64 |

### Opcionais

| Atributos | Tipo | Descrição |
| :-------- | :--: | :-------- |
|           |      |           |

---

## Request Body

#### URL

Método

`POST` https://www.plugchat.com.br/api/whatsapp/send-image-status

#### Body

```json
{
  "image": "https://www.plugchat.com.br/imgs/blue.png"
}
```

:::tip Enviar imagem Base64

Se você tem duvidas em como enviar uma imagem Base64 acesse o tópico mensagens "Enviar Imagem", lá você vai encontrar tudo que precisa saber sobre envio neste formato.

:::

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

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/send-image-status.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
