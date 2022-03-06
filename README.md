# Docker PHP Multiple Versions

## Requisitos

- WSL2 (Opcional)
- Docker
- Docker-compose

## Docker
Com o ambiente linux tendo instalado o docker e docker-compose vamos rodar os comandos de forma linear abaixo:

Acessar o diretorio do projeto
```sh
cd /dev_app
```

Acessar o diretorio do projeto PHP74 e gerar imagem docker
```sh
cd /php74
docker build . -t kelvinsev/webserver-php74:1.0
```

Acessar o diretorio do projeto PHP81 e gerar imagem docker
```sh
cd /php74
docker build . -t kelvinsev/webserver-php81:1.0
```

Listar imagens geradas e confirmar a criação das imagens acima
```sh
docker images
```

Voltar o diretório raiz do projeto e executar o docker-compose
```sh
cd /dev_app
docker-compose up -d
```

Com os passsos acima realizados com sucesso, os containers estarão online e para validar o funcionamento das multiplas versões do PHP acesse no navegador http://localhost:8074/php74/ para o PHP 7.4 e http://localhost:8081/php81/ para o PHP 8.1