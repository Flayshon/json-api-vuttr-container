# Desafio Dev. Back-End Bossabox

Os requisitos fornecidos podem ser revisados [aqui](https://www.notion.so/Dev-Back-End-04cfd92927a045f6914ab1e2c9002c02)

## Informações básicas

O projeto foi desenvolvido com o framework Laravel e utiliza o Docker como ferramenta de conteinerização. Os testes foram implementados utilizando a estrutura padrão do framework com PHPUnit.

## Dependências

É necessário que o Docker esteja instalado e executando normalmente.

## Rodando o projeto

1) No diretório /src, inclua o arquivo com as variáveis de ambiente utilizando o comando `cp .env.example .env`

2) Na pasta raiz do projeto, execute os seguintes comandos

`docker-compose build`

``docker-compose run --rm --user `id -u`:`id -g` composer install``

`docker-compose up -d`

`docker-compose exec php php /var/www/html/artisan migrate`
