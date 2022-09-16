---
id: create-generic-fields
title: Criar campo genérico
---

## Método

#### /create-generic-field

`POST` https://www.plugchat.com.br/api/integrations/create-generic-field

---

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

---

## Conceituação

Nesse método você será capaz de criar ou alterar um campo genérico.

---

## Atributos

### Obrigatórios

| Atributos |  Tipo  | Descrição              |
| :-------- | :----: | :--------------------- |
| phone     | string | Telefone do chat       |
| label     | string | Nome do campo genérico |

### Opcionais

| Atributos |  Tipo  | Descrição               |
| :-------- | :----: | :---------------------- |
| value     | string | Valor do campo genérico |

## Request Body

```json
{
  "phone": "554499999999",
  "label": "Nome",
  "value": "Valor"
}
```

---

## Response

### 200

```json
{"success": true}
```

### 401

Neste caso certifique que esteja enviando o corretamente o Authorization na headers e que o mesmo seja válido.

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---
