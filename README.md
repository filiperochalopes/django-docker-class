# Aplicação Django-Docker

Essa é uma plicação para estudo da stack django com docker e uso de alguns pacotes específicos como DjangoRestFramework, Django-Sass, dentre outros. Happy Coding!

## Python

***Definição de Python***

## Framework

***Definição de Framework e Django***

## Docker

***Definição de Docker***

## Class 1 - Criando o projeto

Para criar uma aplicação Docker precisamos ter o docker intalado, com os pacotes já listados em `requirements.txt` e o `Dockerfile` já escrito executar os seguintes comandos no terminal:

```sh
# Instala as dependências python no container lucas:latest com as regras do Dockerfile
docker build . --no-cache -t lucas:latest
# Acessa o container docker para realizar criação do projeto django
docker run -p 8051:8000 -it --volume=`pwd`:/usr/src/app lucas:latest bash
# Cria projeto Django
django-admin startproject app
# Ao sair do docker com Ctrl+D mude o dono da pasta para seu usuário
sudo chown -R $(id -gn) app
# Executa o projeto que poderá ser acessado na porta 8051
docker run -p 8051:8000 -it --volume=`pwd`:/usr/src/app lucas:latest
```

## Class 2 - Criando a aplicação

Criar uma aplicação chamada `core`, em vez de `polls` como o tutorial abaixo sugere, que terá uma página escrita `Hello World` ao acessar a rota `/hello-world`.

[https://docs.djangoproject.com/pt-br/3.2/intro/tutorial01/](https://docs.djangoproject.com/pt-br/3.2/intro/tutorial01/#creating-the-polls-app)