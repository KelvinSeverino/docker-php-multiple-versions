#Informa o Container base para baixar do Docker Hub
FROM ubuntu:20.04

#Setando variavel
ENV timezone=America/Sao_Paulo

#Comandos para rodar no ubuntu
RUN apt-get update && \
    ln -snf /usr/share/zoneinfo/${timezone} /etc/localtime && echo ${timezone} > /etc/timezone && \
    apt-get install -y apache2 && \
    apt-get install -y software-properties-common && \
    add-apt-repository ppa:ondrej/php && \
    apt-get update && \
    apt-get install -y php7.4 && \    
    apt-get install -y php7.4-mysql && \
    apt-get install -y php-xdebug

#Comandos para habilitar modulo htacess do apache2 e configurar apache2.conf
RUN a2enmod rewrite && \
    echo '\n<Directory "/var/www/html">\n'\
    '    AllowOverride All\n'\
    '</Directory>' >> /etc/apache2/apache2.conf
    
#Porta de Comunicacao
EXPOSE 80

#Diretorio de Trabalho
WORKDIR /var/www/html

#Comando para serem rodados ao final do build
ENTRYPOINT /etc/init.d/apache2 start && /bin/bash