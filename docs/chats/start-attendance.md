---
id: start-attendance
title: Iniciar Atendimento
---

## Método

#### /start-attendance

`POST` https://app.plugchat.com.br/api/integrations/start-attendance

---

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

---

## Conceituação

Nesse método você será capaz de iniciar um atendimento com um operador ou com vários.

É possível também informar o id de um departamento e iniciar o atendimento no departamento informado.

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| phone | string | telefone do chat |
| operators | string[] | Um array com os id dos operadores que atenderão o chat |

### Opcionais

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| departmentId | string | Identificador do departamento que o chat irá pertencer |

## Request Body

```json
{
  "phone": "554499999999",
  "operators": ["OPERADOR-ID-1", "OPERADOR-ID-2"],
  "departmentId": "id do departamento"
}
```

---

## Response

### 200

Exemplo - Caso seja iniciado o atendimento o retorno será:

```json
true
```

---

Exemplo - Caso o chat já esteja em atendimento o retorno será:

| Atributos | Tipo | Descrição |
| :-- | :-- | :-- |
| status | string | Status do atendimento |
| message | string | Mensagem para descrever a situação do atendimento |
| attendanceNumber | number | Número do atendimento |
| operators | Operators[] | Operadores que estão participando do atendimento |

#### Operators

| Atributos | Tipo   | Descrição        |
| :-------- | :----- | :--------------- |
| id        | string | Id do operador   |
| name      | string | Nome do operador |

```json
{
  "status": "progress",
  "message": "chat is already in service",
  "attendanceNumber": 9999,
  "operators": [
    {
      "id": "OPERADOR-ID-1",
      "name": "Fulano de Tal"
    }
  ]
}
```

### 401

Neste caso certifique que esteja enviando o corretamente o Authorization na headers e que o mesmo seja válido.

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---
