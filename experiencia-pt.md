# Nossa experiência integrando o Genie ao Streamlit App no Databricks

Começamos o projeto criando um Databricks App.  
Para isso, acessamos o menu lateral e fomos até Compute → Apps → Create App.  
Selecionamos o tipo Streamlit, marcamos a opção Data App, escolhemos o SQL Warehouse desejado e definimos um nome para a aplicação.

A criação leva alguns minutos para ser concluída, mas logo a aplicação fica pronta para edição e deploy.

---

## Treinando o Genie

Com a base de dados carregada, treinamos o Genie para que ele reconhecesse os dados e pudesse respondê-los via linguagem natural.

---

## O desafio da integração

Nosso maior desafio foi: como conectar o Genie ao app de forma interativa?

Após bastante pesquisa e tentativa, encontramos o repositório do [@datasciencemonkey](https://github.com/datasciencemonkey), que nos ajudou a entender como a integração via API funciona.

---

## O que aprendemos

A partir da estrutura dele, conseguimos:

- Entender como capturar e utilizar o `space_id`
- Iniciar uma `conversation_id`
- Enviar e receber mensagens com `message_id`
- Configurar corretamente o `DATABRICKS_HOST` e o token pessoal (PAT)
- Exibir respostas do Genie de forma dinâmica na tela

Com isso, conseguimos criar um app que conversa com o Genie diretamente dentro da nossa aplicação Streamlit. O resultado ficou assim:

![Interface interativa com o Genie](img1)

---

Essa foi uma ótima oportunidade para entender melhor como funcionam os Databricks Apps, o SDK e a estrutura da API do Genie. Registramos aqui como referência e para ajudar outros que estejam explorando esse tipo de integração.
