# imagem base
FROM nginx:1.15.0-alpine

# atualiza pacotes do apk e instala o bash
RUN apk update && apk add bash

# deleta default.conf (arquivo de configuração padrão do nginx) de /etc/nginx/conf.d
RUN rm /etc/nginx/conf.d/default.conf

# copia nginx.conf da pasta raiz para /etc/nginx/conf.d
COPY ./nginx.conf /etc/nginx/conf.d