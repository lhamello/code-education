# Jornada Microserviços


*******
Índice
 1. [Configurando o Projeto](#configurandoprojeto)
 2. [Rondando a Aplicação](#rodandoaplicacao)
*******

<div id='configurandoprojeto' />  

## Configurando o Projeto  

Dentro da pasta do projeto (`jornada-microservicos`) foi criada a pasta chamada `product_service`.

Na pasta `product_service` foi criado o [Dockerfile](https://github.com/lhamello/code-education/blob/master/jornada-microservicos/product_service/Dockerfile) para o serviço de produtos.

Também foi criado o arquivo `docker-compose.yml` que define nosso serviço de produtos e também os serviços do `mysql`, `redis` e `nginx`.

Foi criada a pasta `.docker`, a quak contém as configurações do `nginx`e também seu próprio `Dockerfile`. Também contém a pasta `dbdata` responsável por mapear o volume do `mysql`.

Por último instalamos o laravel rodando o seguinte comando: 
```sh
$ composer create-project --prefer-dist laravel/laravel blog
```

Então copiei tudo o que foi criado na pasta `blog` para a raiz da pasta `product_service` e então deletei a pasta blog.

<div id='rodandoaplicacao' />  

## Rondando a Aplicação

Para executarmos nossa aplicação, utilizamos o comando:
```sh
$ docker-compose up -d
```

Este comando faz subir nossos serviços, necessário estar na raiz de `product_service` para executar este comando.

Depois de subirmos os serviços, executamos o comando:
```sh
$ docker-compose exec productapp bash
```

Com este comando, acessamo o bash do conteiner do serviço de produtos e então podemos executar o comando:
```sh
$ php artisan migrate
```

Este comando será o responsável por criar o banco de dados.