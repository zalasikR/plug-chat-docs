---
id: send-button-list
title: Enviar texto com botões
---

## Método

#### /send-button-list

`POST` https://app.plugchat.com.br/api/whatsapp/send-button-list

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

---

## Conceituação

Neste método você poderá enviar mensagens de texto com botões de ação, o conteudo do botão ex: SIM / Não, poderão ser escolhidos pelo usuário e será utilizado como resposta da mensagem enviada junto com os botões.

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| phone | string | Telefone (ou ID do grupo para casos de envio para grupos) do destinatário no formato DDI DDD NUMERO Ex: 551199999999. **IMPORTANTE** Envie somente números, sem formatação ou máscara |
| message | string | Texto a ser enviado |
| buttonList | buttonList | Objeto do tipo botão |

### Opcionais

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| delayMessage | number | Nesse atributo um delay é adicionado na mensagem. Você pode decidir entre um range de 1~15 sec, significa quantos segundos ele vai esperar para enviar a próxima mensagem. (Ex "delayMessage": 5, ). O delay default caso não seja informado é de 1~3 sec |

### Button List

| Atributos |  Tipo  | Descrição                     |
| :-------- | :----: | :---------------------------- |
| buttons   | button | lista de botões a ser enviado |

### Button

| Atributos |  Tipo  | Descrição          |
| :-------- | :----: | :----------------- |
| label     | string | Texto para o botão |

### Opcionais Button

| Atributos |  Tipo  | Descrição              |
| :-------- | :----: | :--------------------- |
| id        | string | Identificador do botão |

---

## Request Body

```json
{
  "phone": "5511999999999",
  "message": "Plug-chat é Bom ?",
  "buttonList": {
    "buttons": [
      {
        "id": "1",
        "label": "Ótimo"
      },
      {
        "id": "2",
        "label": "Excelênte"
      }
    ]
  }
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

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/send-button-list.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
