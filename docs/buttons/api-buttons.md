---
id: api-buttons
title: Como usar?
---

## Sobre

Os botões tem 3 valores, o nome do botão, a url da sua api e o método que sera utilizado ( GET ou POST), na sua api é necessário esperar alguns atributos (phone, name, genericFields, email, city, observation), recebendo esses atributos estaremos esperando 3 tipos de resposta da sua api, 1º - message, em message estaremos esperando um mensagem de texto, que será enviada no chat, 2º - modal, em modal estaremos esperando alguma informação que será exibida na tela para o usuário que clicou no botão, 3º - null, aqui apenas daremos um retorno se a chamada deu certo ou não.

---

## Atributos

| Atributos | Tipo | Descrição |
| :-- | :-: | :-- |
| phone | string | Número de telefone do contato selecionado |
| name | string | Nome do contato selecionado |
| genericFields | Array[] | Array de objetos com nome e valor dos campos personalizados |
| email | string | E-mail do contato selecionado |
| city | string | Cidade do contato selecionado |
| observation | string | Observação do contato selecionado |

---

### POST

Se seu botão for do tipo POST enviaremos informações pelo body da requisição.

## Request Body

Exemplo

```json
{
  "phone": "5544999999999",
  "name": "Nome do contato",
  "genericFields": [
    {
      "name": "nome do campo",
      "value": "conteudo do campo"
    }
  ],
  "email": "E-mail",
  "city": "Cidade",
  "observation": "Observação"
}
```

---

### GET

Se seu botão for do tipo GET enviaremos informações pelos parametros da url da sua api.

## Request Params

Exemplo

```json
"URL_DA_SUA_API?phone={phone}&name={name}&genericFields={genericFields}&email={email}&city={city}&observation={observation}"
```
