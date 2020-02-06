# Desafio Dev. Back-End Bossabox

Os requisitos fornecidos podem ser revisados [aqui](https://www.notion.so/Dev-Back-End-04cfd92927a045f6914ab1e2c9002c02)

## Vídeo de apresentação deste projeto

[Apresentação gravada com a ferramenta Loom](https://www.loom.com/share/e21ef05296da4a879971f4686156c934)

## Informações básicas

O projeto foi desenvolvido com o framework Laravel e utiliza o Docker como ferramenta de conteinerização. Os testes foram implementados utilizando a estrutura padrão do framework com PHPUnit.

## Dependências

- É necessário que o Docker e Docker-Compose estejam instalados e executando normalmente.
- As portas 3000, 5532 e 9000 precisam estar livres. Caso necessário, pode-se alterar esses valores no arquivo `docker-compose.yml`

## Rodando o projeto

1) O repositório principal deve ser clonado com o parâmetro --recurse-modules, pois a pasta src tem seu próprio repositório

`git clone --recurse-submodules https://github.com/Flayshon/json-api-vuttr-container.git`

2) No diretório /src, inclua o arquivo com as variáveis de ambiente utilizando o comando `cp .env.example .env`

3) Na pasta raiz do projeto, execute os seguintes comandos

`docker-compose build`

``docker-compose run --rm --user `id -u`:`id -g` composer install``

`docker-compose up -d`

`docker-compose exec php php /var/www/html/artisan migrate`

O status do servidor estará acessivel em http://localhost:3000

Os endpoints deverão ser testados usando o prefixo /api/. Por exemplo:

http://localhost:3000/api/tools
http://localhost:3000/api/tools/1

## Documentação

Disponível no diretório /docs. Elaborada utilizando a sintaxe do API Blueprint e compilada para HTML utilizando o parser Aglio, conforme especificado nos requisitos.

## Testes

Os testes podem ser realizados rodando o executável do PHPUnit no container correspondente

``docker-compose run --rm --user `id -u`:`id -g` php /var/www/html/vendor/bin/phpunit``

## Autenticação

A autenticação via JWT está implementada no branch develop, utilizando o mesmo padrão de rotas do master
