---
id: send-message-image
title: Enviar imagem
---

## Método

#### /send-image

`POST` https://app.plugchat.com.br/api/whatsapp/send-image

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

---

## Conceituação

Método responsavel por enviar imagens para os seus chats você pode trabalhar com as imagens de 2 formas que são:

- Por Link, onde você tem uma imagem hospedada em algum lugar da internet e envia apenas o link da mesma.

- Por Base64, se você optar por esta opção precisará ter em sua aplicação um método para converter a imagem em Base64, para ter certeza que sua conversão funcionou copie o Base64 gerado e cole na barra de endereço do seu navegador, caso seja uma imagem válida seu navegador vai conseguir renderiza-la, caso o navegador não consiga, revise seu método :).

  **_ IMPORTANTE _** se optar por base64 antes do binário você precisa adicionar a seguinte expressão ** data:image/png;base64, \*_ seu codigo base64 _\* **

Você pode fazer um teste com este tipo de envio utilizando um conversor online de imagens para Base64.

Exemplos:

[conversor 1]

[conversor 2]

[conversor 1]: https://www.base64-image.de/
[conversor 2]: https://base64.guru/converter/encode/image

### Tamanho e formatos

O Whatsapp limita o tamanho de arquivos e sua politica muda constantemente, por isso sempre recomendamos a verificação direto no site do próprio Whatsapp.

Neste [link] você encontra tudo que precisa saber sobre formatos e tamanhos de arquivos.

[link]: https://developers.facebook.com/docs/whatsapp/api/media

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| phone | string | Telefone (ou ID do grupo para casos de envio para grupos) do destinatário no formato DDI DDD NUMERO Ex: 551199999999. **IMPORTANTE** Envie somente números, sem formatação ou máscara |
| image | string | Link da imagem ou seu Base64 |

### Opcionais

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| caption | string | Titulo da sua imagem |
| messageId | String | Atributo utilizado para responder uma mensagem do chat, basta adicionar o messageId da mensagem que queira responder neste atributo |
| delayMessage | number | Nesse atributo um delay é adicionado na mensagem. Você pode decidir entre um range de 1~15 sec, significa quantos segundos ele vai esperar para enviar a próxima mensagem. (Ex "delayMessage": 5, ). O delay default caso não seja informado é de 1~3 sec |

---

## Request Body

URL

```json
{
  "phone": "5511999999999",
  "image": "https://www.plugchat.com.br/imgs/blue.png"
}
```

BASE64

```json
{
  "phone": "5511999999999",
  "image": "data:image/png;base64,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",
  "caption": "Logo"
}
```

---

## Response

### 200

| Atributos | Tipo   | Descrição      |
| :-------- | :----- | :------------- |
| zaapId    | string | id no plug     |
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

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/send-image.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
