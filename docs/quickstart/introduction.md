---
id: introduction
title: Introdução
slug: /
---

## Plug-Chat - Multi atendimentos, via Whatsapp

**Plug chat** foi pensado e desenvolvido para ser uma ferramenta que facilita a vida de quem **precisa prestar atendimentos via Whatsapp**, um aplicativo simples e objetivo, sendo assim, vou te contar um pouco mais.

---

## Mas o que é o Plug-Chat?

Você provavelmente já deve saber, mas vamos reafirmar!

**Plug-Chat** É uma plataforma de multi atendimentos com diversos operadores integrados em um só numero de Whatsapp, atendendo simultaneamente. O Plug Chat te fornece tudo que você precisa! Métricas sobre atendimentos, integração com trello para criar tarefas apartir de um atendimento e pesquisa de satisfação, garantindo a qualidade do seu suporte.


:::important Importante

Recentemente o Whatsapp lançou a funcionalidade de múltiplos dispositivos, isso **permite** que você conecte até **4** dispositivos no seu Whatsapp. Caso essa opção **esteja ativada** em seu celular, você poderá utilizar o Plug-Chat, sem a necessidade de manter o telefone conectado a internet a todo momento, isso evitará problemas de conexão.

:::

---

## Tábom! mas o que dá para fazer com ele?

De forma bem direta, tudo que você faz com Whatsapp Web você poderá fazer utilizando nosso serviço. 
E existe algumas outras funcionalidades como o top 10 clientes que mais enviam mensagens, etiquetas de marcações, mensagens rapidas, etc...

---

## Tecnicamente, como funciona o fluxo de envio?

Para exemplificar, segue os passos de envio de uma mensagem de texto simples:

1. Você envia via API uma mensagem para o Plug;

2. O Plug adiciona em uma fila e te retorna o ID da mensagem;

3. Sua instância processa a fila enviando para o WhatsApp;

4. Seu Webhook de delivery é chamado quando sua mensagem for enviada;

5. Assim que o destinatário receber a mensagem, o Webhook de message-status é chamado informando RECEIVED e

6. Por fim quando o destinatário ler a mensagem o messages-status é chamado informando READ

---

## Limites

Iniciei por este tópico porque é bem comum as pessoas perguntarem sobre quais os limites de envios com Plug. Nós **NÃO TEMOS LIMITE** para número de mensagens enviadas! Mas é importante você entender que esta utilizando uma sessão do Whatsapp Web, então o padrão de utilização precisa ser compatível, além disso sempre recomendamos que você leia atentamente as políticas estabelecidas pelo proprio Whatsapp em sua pagina oficial https://www.whatsapp.com/legal.

---