---

id: get-operators-online

## title: Endpoint - Get Operators Online

## Método

#### Endpoint

`GET` [https://app.plugchat.com.br/api/account/get-operators-online?id=SUA\_ID\_AQUI](https://app.plugchat.com.br/api/account/get-operators-online?id=SUA_ID_AQUI)

---

## Header

```https
Authorization: Bearer SEU_TOKEN_AQUI
Content-Type: application/json
```

\:::caution Atenção
O Plugchat não aceita requisições sem autenticação ou com URLs que não utilizam HTTPS.
\:::

---

## Conceituação

Esse endpoint retorna a **lista de operadores que estão online** em uma conta Plugchat, identificada por seu ID. Útil para monitoramento em tempo real, distribuição de atendimentos ou exibição de status em dashboards.

---

## Parâmetros

### Obrigatórios (Query String)

| Parâmetro | Tipo   | Descrição               |
| --------- | ------ | ----------------------- |
| id        | string | ID da conta no Plugchat, ela fica na URL do chat do operador |

---

## Exemplo de Requisição

```http
GET https://app.plugchat.com.br/api/account/get-operators-online?id=1234567890

Authorization: Bearer SEU_TOKEN_AQUI
Content-Type: application/json
```

---

## Response

### 200 - Sucesso

```json
{
  "data": [
    {
      "id": "52a8dce4-b49c-4936-ad8c-2c9e103b43",
      "lastChanged": 1747674466027,
      "name": "Geovana",
      "state": "online"
    },
    {
      "id": "53619765-3060-4c53-9698-baf4ee0c2",
      "lastChanged": 1747661587355,
      "name": "Ryan",
      "state": "offline"
    },
    {
      "id": "b16ad2e8-7253-421e-bc77-9730027c75",
      "lastChanged": 1747676996340,
      "name": "Ana Flávia ",
      "state": "online"
    }
  ]
}
```

### 401 - Não autorizado

Verifique se o token de autenticação foi enviado corretamente.

### 400 - Requisição malformada

Verifique se o parâmetro `id` foi informado.

---

## Observações

* Utilize esse endpoint para consultar se o operador está botão de offline ou online
