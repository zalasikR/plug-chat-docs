---
id: finish-attendance
title: Finalizar Atendimento
---

## Método

#### /finish-attendance

`POST` https://app.plugchat.com.br/api/integrations/finish-attendance

---

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

---

## Conceituação

Nesse método você será capaz de finalizar um atendimento com um operador.

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| phone | string | telefone do chat |
| autoTransfer | boolean | transferir para departamento Geral após a finalização |
| operatorId | string | o id do operador que finalizou o chat |

## Request Body

```json
{
  "phone": "554499999999",
  "operatorId": "OPERADOR-ID",
  "autoTransfer": true
}
```

---

## Response

### 200

Exemplo - Caso seja finalizado o atendimento o retorno será:

```json
{
  "success": true,
  "message": "Ticket closed successfully",
  "chatFounded": true
}
```

---

### 401

Neste caso certifique que esteja enviando o corretamente o Authorization na headers e que o mesmo seja válido.

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---
