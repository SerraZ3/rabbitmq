# RabbitMQ

Estudo com fila usando [RabbitMQ](https://www.rabbitmq.com/)

## Instalação

Necessário instalar o servidor RabbitMQ

Instalação no Ubuntu 20.04 LTS

Pacotes necessários:

```shellscript
$ sudo apt-get install wget apt-transport-https -y
```

Assinatura do repositório:

```shellscript
$  wget -O- https://www.rabbitmq.com/rabbitmq-release-signing-key.asc | sudo apt-key add -
```

Adicionando repositório:

```shellscript
$ echo "deb https://dl.bintray.com/rabbitmq-erlang/debian focal erlang-22.x" | sudo tee /etc/apt/sources.list.d/rabbitmq.list
```

Instalando rabbitmq-server:

```shellscript
$ sudo apt-get install rabbitmq-server -y --fix-missing
```

Status do servidor:

```shellscript
$ sudo systemctl status rabbitmq-server
```

---

Caso queira pode instalar um gerenciador de filas para monitoramento

```shellscript
$ sudo rabbitmq-plugins enable rabbitmq_management
```

Altere o campo `<SUA_SENHA>`

```shellscript
$ sudo rabbitmqctl add_user admin <SUA_SENHA>
```

```shellscript
$ sudo rabbitmqctl set_user_tags admin administrator
```

Ele ficará rodando em http://localhost:15672
