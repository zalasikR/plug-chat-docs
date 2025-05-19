---
id:id: group-invitation-metadata

title: Metadata do Grupo por Convite
---

## Método

#### /group-invitation-metadata

`GET` https://app.plugchat.com.br/api/whatsapp/group-invitation-metadata?url={ **URL** **DO** **CONVITE**}

## Header
#### Toda requisição http feita precisa passar sua header de autorização.


| Key            | Value                   |
| :------------: |   :---------------:     |
| Authorization: |   1nEFbU3EktLnV7LIIzX   |

## Conceituação

Este método retorna o metadata do grupo com todas as informações do grupo e de seus participantes.

:::caution Atenção

No dia 4 de novembro de 2021 o whatsapp alterou o formato da criação de novos grupos, antes: "phone": "5511999999999-1623281429" agora: "phone": "120363019502650977-group"

:::

---

## Response

### 200

| Atributos    | Tipo         | Descrição                             |
| :----------- | :----------- | :------------------------------------ |
| phone        | string       | ID/Fone do Grupo                      |
| owner        | string       | Número do criador do grupo            |
| subject      | string       | Nome do grupo                         |
| creation     | timestamp    | Timestamp da data de criação do grupo |
| participants | array de string | com dados dos participantes        |

Array String (participants)

| Atributos    | Tipo   | Descrição                                         |
| :----------- | :----- | :------------------------------------------------ |
| phone        | string | Fone do participante                              |
| isAdmin      | string | Indica se o participante é administrador do grupo |
| isSuperAdmin | string | Indica se é o criador do grupo                    |
| short        | string | Nome curto do participante                        |
| name         | string | Nome do participante                              |

**Exemplo**

```json

Forma antiga -
  {
    "phone": "5511999999999-1623281429",
    "owner": "5511999999999",
    "subject": "Meu grupo no Plug",
    "creation": 1588721491000,
    "participants": [
      {
        "phone": "5511888888888",
        "isAdmin": false,
        "isSuperAdmin": false
      },
      {
        "phone": "5511777777777",
        "isAdmin": true,
        "isSuperAdmin": false,
        "short": "ZAPIs",
        "name": "ZAPIs Boys"
      }
    ],
    "subjectTime": 1617805323000,
    "subjectOwner": "554497050785"
  }

  ------------------------------------

  Forma nova -
  {
  "phone": "120363019502650977-group",
  "owner": "5511999999999",
  "subject": "Meu grupo no Plug",
  "creation": 1588721491000,
  "participants": [
    {
      "phone": "5511888888888",
      "isAdmin": false,
      "isSuperAdmin": false
    },
    {
      "phone": "5511777777777",
      "isAdmin": true,
      "isSuperAdmin": false,
      "short": "Plug",
      "name": "Plug Boys"
    }
  ],
  "subjectTime": 1617805323000,
  "subjectOwner": "554497050785"
}

```

### 405

Neste caso certifique-se de que está enviando corretamente a especificação do método, ou seja, verifique se você enviou o POST ou GET conforme especificado no início deste tópico.

### 415

Caso você receba um erro 415, certifique-se de adicionar nos headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/group-invitation-metadata.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
