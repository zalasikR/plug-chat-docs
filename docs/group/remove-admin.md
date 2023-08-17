---
id: remove-admin
title: Remover admin do grupo
---

## Método

#### /remove-admin

`POST` https://www.plugchat.com.br/api/whatsapp/remove-admin

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

## Conceituação

Este método é reponsável por remover um ou mais admistradores de um grupo.

:::caution Atenção

No dia 4 de novembro de 2021 o whatsapp alterou a formato da criação de novos grupos, antes: "phone": "5511999999999-1623281429" agora: "phone": "120363019502650977-group"

:::

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| groupId | string | id/fone do grupo |
| phones | array string | Array com os número(s) a ser(em) removido(s) da administração do grupo |

### Opcionais

| Atributos | Tipo | Descrição |
| :-------- | :--: | :-------- |

---

## Request Body

#### URL

`POST` https://www.plugchat.com.br/api/whatsapp/remove-admin

#### Body

```json

Forma antiga -
  {
    "groupId": "5511999999999-1623281429",
    "phones": ["5544999999999", "5544888888888"]
  }

  -------------------------------------------------

Forma nova -
  {
    "groupId": "120363019502650977-group",
    "phones": ["5544999999999", "5544888888888"]
  }

```

````

---

## Response

### 200

| Atributos | Tipo    | Descrição                                           |
| :-------- | :------ | :-------------------------------------------------- |
| value     | boolean | true caso tenha dado certo e false em caso de falha |

**Exemplo**

```json
{
  "value": true
}
````

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no início deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/remove-admin.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
