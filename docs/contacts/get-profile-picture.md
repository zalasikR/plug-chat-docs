---
id: get-profile-picture
title: Pegar imagem do contato
---

## Método

#### /profile-picture

`GET` https://www.plugchat.com.br/api/whatsapp/profile-picture

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

---

## Conceituação

Este método é responsável por retornar a url com a imagem do contato atualizada.

Como já dito no tópico anterior **Lembre-se**

Se você pretente armazenar a imagem do seu contato observe que sempre retornamos no get-contacts o atributo imgUrl com ela para você, porém é importante lembrar que esta fica disponível por apenas **48 horas**, após este periodo o link da imagem é excluido pelo próprio Whatsapp. Sugerimos que caso precise atualizar a imagem do seu contato você utilize o proximo método desta documentação, o **get-profile-picture**.

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

`GET` https://www.plugchat.com.br/api/whatsapp/profile-picture?phone=551199999999

---

## Response

### 200

| Atributos | Tipo   | Descrição                 |
| :-------- | :----- | :------------------------ |
| link      | string | Url com a foto do contato |

Exemplo

```json
[
  {
    "link": "Url com a foto do contato"
  }
]
```

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no início deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/get-profile-picture.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
