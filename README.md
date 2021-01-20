Introdução





- Requisitos:

- Docker instalado
- Docker compose
- Ngrok




### Como rodar


- É necessário ter instalado ou instalar o ngrok. Também é preciso ter uma conta [https://ngrok.com/](https://ngrok.com/).
- Depois de fazer o [download do ngrok](https://ngrok.com/download), na pasta execute o seguinte comando:

```bash
./ngrok http 5005
```

- Depois faça o clone do repositório
- Abra com um editor de texto

- Para que o bot funcione na web e no telegram, será preciso fazer algumas configurações antes.
Primeiro a da web. O ngrok fornecerá no terminal uma url https, como por exemplo na imagem abaixo:

<img>

Copie a url fornecida https e troque no arquivo `credentials.yml` nos locais informados em rest e telegram.

- Para que o telegram funcione corretamente, é preciso criar um bot pelo [Telegram](https://rasa.com/docs/rasa/connectors/telegram/) usando o BotFather, link.
- Adicione o nome do bot e o token no arquivo `credentials.yml`

- Execute o comando 

```bash
sudo docker-compose up
```

- Para ter acesso ao webchat acesse:

[http://localhost:8080/](http://localhost:8080/)

- E converse com o bot no telegram que ele já estará funcionando!



Pode acessar o bot de forma web usando o Rasa X e o Telegram.

- personalidade do bot
- a mais, novas infos sobre a vacina
- Banco de dados?


Próximos passos:
- Fazer um webhook para salvar conversas em um banco de dados para saber o que e como os usuários estão se comunicando com o bot, podendo assim retreinar e melhorar a usabilidade.
- Fazer deploy do (Rasa X?) para poder compartilhar o bot de forma web com os os usuários testes e usuários em geral para poder captar mais dados de como as pessoas interagem com o bot. E utilizando o serviço(interface) do Rasa X, é possível corrigir caso as intenções tenham sido classificadas de forma errada, para então retreinar o modelo.
feedback, coletar conversas entre usuários e o bot, revisar conversas e melhorar o bot com base no que aprendeu com os usuários
Com o rasa x, tem acessos as mensagems do telegram também pela interface, quando estiver em deploy. Usar o certbot ...