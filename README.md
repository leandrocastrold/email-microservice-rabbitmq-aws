# Microsserviço de email - Mensageria, AWS e Docker

Projeto desenvolvido para pôr em prática conhecimentos sobre:

- Mensageria, com o *Message Broker* **RabbitMQ**
- Serviço de envios de email (*SES*) com o **AWS** (*Amazon Simple Email Service*)
- Banco de Dados **PostgreSQL**
- Conteineres, com **Docker**


Consiste em um microsserviço que recebe dados de um email (via requisição *HTTP* ou **RabbitMQ**) e o envia ao destinatário, utilizando o *SES* da **AWS**. As informações sobre o email, como o corpo e status, são salvos no banco de dados (**PostgreSQL**). 

O projeto utiliza um conteiner do **Docker** para subir o banco de dados, com um arquivo **docker-compose.yml**.

## Configuração

No arquivo *application.properties*, insira suas credenciais **AWS** nos campos: 
```
spring.mail.host= [SERVIDOR_AWS_ESCOLHIDO]
spring.mail.port=587
spring.mail.username= [STRING COM USERNAME GERADO NA AWS]
spring.mail.password= [STRING DE SENHA GERADA NA AWS]

```

Insira também suas credenciais do **RabbitMQ**:

```
spring.rabbitmq.addresses= [STRING GERADA NO CLOUDAMPQ]
spring.rabbitmq.queue= [NOME DA FILA]
```


## Execução

Para subir a banco de dados **PostgreSQL** num conteiner **Docker**, inicialize o *docker-compose.yml*, com o comando:

`
docker compose up
`
<hr>

Projeto baseado no tutorial da arquiteta de software e youtuber Michelli Brito.
