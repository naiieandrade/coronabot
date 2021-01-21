## Conheça a Esther

Esther é um chatbot desenvolvido com o RASA (versão 2) para responder perguntas frequentes sobre o coronavírus. Está em fase de construção, e para a primeira versão as perguntas foram baseadas do [FAQ da Fio Cruz](https://mooc.campusvirtual.fiocruz.br/rea/coronavirus/faq.html).


__________________________


### Como foi construído

Esther é um chatbot desenvolvido com o RASA versão 2. 


### Como rodar a Esther?

#### Requisitos:

Antes de rodar a Esther é necessário se atentar aos programas que já devem estar instalados:

- [Docker](https://docs.docker.com/engine/install/ubuntu/)
- [Docker compose](https://docs.docker.com/compose/install/)
- [Ngrok](https://ngrok.com/download)


#### Como rodar

- Além da instalação do ngrok, também é preciso [criar uma conta](https://ngrok.com/).
- Vá até a pasta onde instalou o ngrok e execute o seguinte comando:

```bash
./ngrok http 5005
```

- Depois faça o clone do repositório (se não for o caso, continue)
- Abra o projeto com um editor de texto de sua preferência
- Para que o bot funcione na web e no telegram, será preciso fazer algumas configurações antes.
Primeiro a da web. O ngrok fornecerá no terminal uma url https, como por exemplo na imagem abaixo:

![ngrok terminal](img/ngrok.png)

Nessa imagem a url fornecia é `https://c8cc457cb043.ngrok.io`. 

Copie a url fornecida https e troque no arquivo `credentials.yml` nos locais informados em `rest` e `telegram`.

**obs:** é necessário fazer este passo porque a conta free não permite edição de domínio, para que facilitasse seria necessário a conta paga para que a url fosse fixa.

- Para que o telegram funcione corretamente, é preciso criar um bot pelo [Telegram](https://rasa.com/docs/rasa/connectors/telegram/) usando o [BotFather](https://t.me/botfather).
- Adicione o nome do bot e o token fornecido pelo BotFather no arquivo `credentials.yml`

- Execute o comando 

```bash
sudo docker-compose up
```


- Para ter acesso ao webchat acesse:

[http://localhost:8080/](http://localhost:8080/)

- Agora pode conversar com o bot no webchat ou telegram que ele já estará funcionando!


### Próximos passos

- Fazer um webhook para salvar conversas em um banco de dados para saber o que e como os usuários estão se comunicando com o bot, podendo assim retreinar e melhorar o modelo aumentando os exemplos e facilitando a usabilidade.
- Fazer deploy da Esther para poder compartilhar o bot de forma web com usuários testes e usuários em geral para poder captar mais dados de interação com o bot. 
- Analisar os dados das conversas salvos para novos insights, melhoria do bot atual e até criação de novas intents que os usuários demonstrem interesse.
- Criação da personalidade da Esther.