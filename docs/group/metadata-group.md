---
id:id: metadata-group

title: Metadata do Grupo
---

## Método

#### /group-metadata

`GET` https://app.plugchat.com.br/api/whatsapp/group-metadata

## Header
#### Toda requisição http feita precisa passar sua header de autorização.


| Key            | Value                   |
| :------------: |   :---------------:     |
| Authorization: |   1nEFbU3EktLnV7LIIzX   |

## Conceituação

Este método retorna o metadata do grupo com todas informações do grupo e de seus partipantes.

:::caution Atenção

No dia 4 de novembro de 2021 o whatsapp alterou a formato da criação de novos grupos, antes: "phone": "5511999999999-1623281429" agora: "phone": "120363019502650977-group"

:::

---

## Atributos

### Obrigatórios

| Atributos |  Tipo  | Descrição        |
| :-------- | :----: | :--------------- |
| groupId   | string | ID/Fone do grupo |

### Opcionais

| Atributos | Tipo | Descrição |
| :-------- | :--: | :-------- |

---

## Request Params

#### URL

`POST` https://www.plugchat.com.br/api/whatsapp/group-metadata/{phone}

---

## Response

### 200

| Atributos    | Tipo         | Descrição                             |
| :----------- | :----------- | :------------------------------------ |
| phone        | string       | ID/Fone do Grupo                      |
| owner        | string       | Numero do criador do grupo            |
| subject      | string       | Nome do grupo                         |
| creation     | timestamp    | Timestamp da data de criação do grupo |
| invitationLink | string     | link de convite do grupo              |
| participants | array string | com dados dos participantes           |

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
    "subject": "Meu grupo no PLug",
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

  ------------------------------------

  Forma nova -
  {
  "phone": "120363019502650977-group",
  "owner": "5511999999999",
  "subject": "Meu grupo no Plug",
  "creation": 1588721491000,
  "invitationLink": "https://chat.whatsapp.com/KN17mskQqLDLALVA0q5E",
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

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/group-metadata.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
