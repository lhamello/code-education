# imagem base
FROM php:7.3.6-fpm-alpine3.9

# apk é o gerenciador de pacotes do linux alpine (como se fosse apt-get)
# --no-cache: configuração para não utilizar cache
RUN apk add --no-cache openssl bash mysql-client nodejs npm

# docker-php-ext-install: permite instalar extensões do PHP
RUN docker-php-ext-install pdo pdo_mysql bcmath

# diretório de trabalho para o container
WORKDIR /var/www

# removendo a pasta html
RUN rm -rf /var/www/html

# criando link da pasta public para a pasta html
RUN ln -s public html

# instalando composer que é o gerenciador de pacotes do php
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# expondo a porta 9000 que é onde o php-fpm irá rodar
EXPOSE 9000

# indica o processo principal que o container irá rodar, após os comandos acima
ENTRYPOINT [ "php-fpm" ]