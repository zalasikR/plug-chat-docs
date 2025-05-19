---
id: delete-product
title: Deletar Produto
---

## Método

#### /products/id-do-produto

`DELETE` https://app.plugchat.com.br/api/whatsapp/products/{{id-do-produto}}

---

## Conceituação

Nesse método você será capaz de deletar um produto pelo seu id

## Response

### 200

| Atributos | Tipo    | Descrição               |
| :-------- | :------ | :---------------------- |
| success   | boolean | Atributo de confirmação |

Exemplo

```json
{
  "success": true
}
```

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/delete-product.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
