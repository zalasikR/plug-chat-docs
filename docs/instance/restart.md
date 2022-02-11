---
id: restart
title: Reiniciar instância
---

## Método

#### /restart

`GET` https://www.plugchat.com.br/api/whatsapp/restart

## Header
#### Toda requisição http feita precisa passar sua header de autorização.


| Key            | Value                   |
| :------------: |   :---------------:     |
| Authorization: |   1nEFbU3EktLnV7LIIzX   |

---

## Conceituação

Este método basicamente é o botão "Reiniciar" do seu sistema operacional ou seja, como todo usuário expert, em casos onde tudo parece dar errado tente control+alt+del ou reinicia!

---

## Response

### 200

```json
{
  "value": true
}
```

### 405

Neste caso certifique que esteja enviando o corretamente a especificação do método, ou seja verifique se você enviou o POST ou GET conforme especificado no inicio deste tópico.

### 415

Caso você receba um erro 415, certifique de adicionar na headers da requisição o "Content-Type" do objeto que você está enviando, em sua grande maioria "application/json"

---

## Code

---

:::note

Não! Você não precisa ler o QRCode se reiniciar a sua instância.
