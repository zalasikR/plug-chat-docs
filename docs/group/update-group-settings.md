---
id: update-group-settings
title: Configurações do grupo
---

## Método

#### /update-group-settings

`POST` https://app.plugchat.com.br/api/whatsapp/update-group-settings

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

## Conceituação

Este método permite você alterar as preferências do grupo.

:::caution Atenção

Atenção somente administradores podem alterar as preferências do grupo.

:::

:::caution Atenção

No dia 4 de novembro de 2021 o whatsapp alterou o formato da criação de novos grupos, antes: "phone": "5511999999999-1623281429" agora: "phone": "120363019502650977-group"

:::

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| phone | string | ID/Fone do grupo |
| adminOnlyMessage | boolean | Somente administradores podem enviar mensagens no grupo |
| adminOnlySettings | boolean | Atributo para permitir que apenas os admins façam edições no grupo |

---

## Request Body

```json

Forma antiga -
  {
    "phone": "5511999999999-1623281429",
    "adminOnlyMessage": true
  }

----------------------------------------

Forma nova -
  {
    "phone": "120363019502650977-group",
    "adminOnlyMessage": true
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

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/update-group-settings.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
