---
id: introduction
title: Introdução
---

## Conceituação

Neste tópico falaremos sobre os **RETORNOS** dos webhooks que utilizamos.

As instâncias do Plugchat fazem requisições com o método **POST** dos eventos realizados por ela para a URL configurada previamente. Para cada requisição há um corpo em JSON específico que será descrito em seguida.

:::caution Importante

Seu endpoint precisa aceitar um **POST**

Esses endpoints são para trocar a URL que a instância irá chamar quando o evento acontecer

:::

## O que é e para que serve?

Segundo o Google, Webhook é um recurso usado na internet para que uma aplicação se comunique com outra, fornecendo dados em tempo real sempre que um evento acontecer. Desta forma os dois sistemas realizam trocas de informações sem que nenhuma ação externa precise ser realizada.

Então se você está se integrando com o Z-API e precisa receber informações pelo WhatsApp, é necessário prover estes end-points na sua aplicação para conseguirmos te avisar sobre tudo que acontece no seu WhatsApp. Ou seja, toda vez que o número conectado receber uma interação, vamos fazer uma requisição com o método POST para a URL configurada previamente. (Para cada requisição há um corpo em JSON específico)

---

### Nossos webhooks

#### When sending message

Responsavel por avisar você que sua mensagem foi entregue ao WhatsApp, mas isso não significa necessáriamente que seu contato a recebeu, para informações de recebimento e leitura você vai precisar observar o webhook de status.

#### Receive

Este webhook será chamado toda vez que alguem interagir com seu número no whatsapp.

#### Status

Este método vai lhe avisar de todas mudanças de status que sua mensagem sofrer, se ela for recebida, lida, respondida ou excluida, ou seja uma mesma mensagem pode passar por varios status, e ter o mesmo status mais de uma vez, que é o caso de respondida.

#### Disconnected

Este webhook será chamado sempre que nosso serviço identificar alguma indisponibiidade na comunicação, seja do seu celular com o whatsapp ou mesmo da conexão entre seu celular e o Plugchat.

---

:::tip Dica

- Não deixe de ler nossa sessão dicas, lá você vai encontrar alguns tópicos de como melhorar sua conexão com Plugchat e ter mais qualidade no serviço.

- Você não precisa configurar todos webhooks, mas quanto mais controle você possuir sobre sua instância será melhor.

:::

:::important Importante

Nunca compartilhe o token authorization.

:::

## Como configurar meu Webhook?

É possível atualizar o webhook de uma instância por dois caminhos diferentes.