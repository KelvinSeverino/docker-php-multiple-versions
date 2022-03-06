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
    apt-get install -y php8.1 && \    
    apt-get install -y php8.1-mysql php8.1-bz2 php8.1-curl php8.1-common php8.1-gd php8.1-gmp php8.1-intl php8.1-mbstring php8.1-soap php8.1-cli php8.1-dev php8.1-zip php8.1-xml php8.1-xmlrpc php8.1-imagick php8.1-redis php8.1-intl php8.1-ldap && \
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