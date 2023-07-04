---
id:id: add-admin

title: Promover admin do grupo
---

## Método

#### /add-admin

`POST` https://www.plugchat.com.br/api/whatsapp/add-admin

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

## Conceituação

Este método é reponsável por promover participamentes do grupo à administradores, você pode provomover um ou mais participamente à administrador.

:::caution Atenção

No dia 4 de novembro de 2021 o whatsapp alterou o formato da criação de novos grupos, antes: "phone": "5511999999999-1623281429" agora: "phone": "120363019502650977-group"

:::

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| groupId | string | ID/Fone do grupo |
| phones | array string | Array com os número(s) do(s) participante(s) a serem promovidos |

### Opcionais

| Atributos | Tipo | Descrição |
| :-------- | :--: | :-------- |

---

## Request Body

#### URL

`POST` https://www.plugchat.com.br/api/whatsapp/add-admin

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
```

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no início deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/add-admin.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
