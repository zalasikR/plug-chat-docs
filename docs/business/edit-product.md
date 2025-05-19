---
id: edit-product
title: Criar/editar Produto
---

## Método

#### /products

`POST` https://app.plugchat.com.br/api/whatsapp/products

---

## Conceituação

Nesse método você será capaz de cadastrar e atualizar um produto no seu catálogo

---

## Atributos

### Obrigatórios

| Atributos   |  Tipo   | Descrição                                      |
| :---------- | :-----: | :--------------------------------------------- |
| currency    | string  | Tipo da Moeda                                  |
| description | string  | Descrição do produto                           |
| images      | string  | Url da imagem do produto                       |
| isHidden    | boolean | Atributo para "esconder" o produto no catálogo |
| name        | string  | Nome do produto                                |
| price       | integer | Preço do produto                               |
| retailerId  | string  | Id do produto                                  |
| url         | string  | Url da rota do Plug                            |

## Request Body

```json
{
  "currency": "BRL",
  "description": "Uma descrição do produto",
  "images": ["https://avatars.githubusercontent.com/u/60630101?s=200&v=4"],
  "isHidden": false,
  "name": "Meu primeiro produto",
  "price": 20,
  "retailerId": "002",
  "url": "https://www.plugchat.com.br/"
}
```

---

## Response

### 200

| Atributos | Tipo   | Descrição     |
| :-------- | :----- | :------------ |
| id        | string | Id do produto |

Exemplo

```json
{
  "id": "4741575945866725"
}
```

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no início deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/edit-product.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
