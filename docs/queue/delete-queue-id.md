---
id: delete-queue-id
title: Apagando msg fila
---

## Método

#### /queue/{zaapid}

`DELETE` https://app.plugchat.com.br/api/whatsapp/queue/{zaapid}

## Header

#### Toda requisição http feita precisa passar sua header de autorização.

|      Key       |        Value        |
| :------------: | :-----------------: |
| Authorization: | 1nEFbU3EktLnV7LIIzX |

## Conceituação

Este método é responsável por deletar uma mensagem dentro de fila aguardando para ser processada.

---

## Atributos

### Obrigatórios

| Atributos | Tipo | Descrição |
| :-------- | :--: | :-------- |
|           |      |           |

### Opcionais

| Atributos | Tipo | Descrição |
| :-------- | :--: | :-------- |
|           |      |           |

---

## Request Params

#### URL exemplo

Método

`DELETE` https://www.plugchat.com.br/api/whatsapp/queue/{zaapid}

---

## Response

### 200

### 405

Neste caso certifique-se que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/delete-queue-id.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
