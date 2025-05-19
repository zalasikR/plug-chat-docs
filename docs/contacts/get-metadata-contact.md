---
id: get-metadata-contact
title: Pegar metadata do contato
---

## Método

#### /contacts/{phone}

`GET` https://app.plugchat.com.br/api/whatsapp/contacts/{phone}

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

---

## Conceituação

Este método é responsável por retornar as informações do metadata do contato.

:::tip Dica sobre imagem do contato

Se você pretente armazenar a imagem do seu contato observe que sempre retornamos no get-contacts o atributo imgUrl com ela para você, porém é importante lembrar que esta fica disponível por apenas **48 horas**, após este periodo o link da imagem é excluido pelo próprio Whatsapp. Sugerimos que caso precise atualizar a imagem do seu contato você utilize o próximo método desta documentação, o **get-profile-picture**.

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

`GET` https://www.plugchat.com.br/api/whatsapp/send-textcontacts/5511999999999

---

## Response

### 200

| Atributos | Tipo | Descrição |
| :-- | :-- | :-- |
| phone | string | Phone do contato |
| name | string | **Nome e sobrenome** do contato, só vai retornar preenchido caso você tenha o número em seus contatos |
| short | string | **Nome** do contato, só vai retornar preenchido caso você tenha o número em seus contatos |
| vname | string | Nome do Vcard do contato, caso ele tenha |
| notify | string | Nome informado nas configurações de nome do Whatsapp |
| imgUrl | string | URL da foto do contato **o Whatsapp apaga após 48hs** |

Exemplo

```json
{
  "name": "Nome e sobrenome do contato",
  "phone": "551199999999",
  "notify": "Nome do contado no Whatsapp",
  "short": "Nome do contato",
  "imgUrl": "url da foto do contato "
}
```

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no início deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/get-metadata-contact.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
