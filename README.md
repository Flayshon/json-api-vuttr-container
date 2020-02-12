# Desafio Dev. Back-End Bossabox

Implementação de uma API para a aplicação VUTTR (Very Useful Tools to Remember) de acordo com os requisitos listados [aqui](https://www.notion.so/Dev-Back-End-04cfd92927a045f6914ab1e2c9002c02).

## Vídeo de apresentação do projeto

[Apresentação gravada com a ferramenta Loom](https://www.loom.com/share/e21ef05296da4a879971f4686156c934)

**Atenção:** o vídeo da apresentação foi publicado antes do recurso de autenticação com JWT ser incluído, além de refinamentos na estrutura de testes e tratamento de exceções.

A versão do projeto que reflete o vídeo apresentado pode ser acessada no branch **presentation**.

## Informações básicas

O projeto foi desenvolvido com o framework Laravel e utiliza o Docker como ferramenta de conteinerização. Os testes foram implementados utilizando a estrutura padrão do framework com PHPUnit.

## Dependências

- É necessário que o Docker e Docker-Compose estejam instalados e executando normalmente.
- As portas 3000, 5532 e 9000 precisam estar livres. Caso necessário, pode-se alterar esses valores no arquivo `docker-compose.yml`

## Rodando o projeto

1) O repositório principal deve ser clonado com o parâmetro --recurse-modules, pois a pasta src tem seu próprio repositório

`git clone --recurse-submodules https://github.com/Flayshon/json-api-vuttr-container.git`

2) No diretório /src, inclua o arquivo com as variáveis de ambiente utilizando o comando

`cp .env.example .env`

3) Na pasta raiz do projeto, execute os seguintes comandos para instalação das dependências e inicialização dos containers

`docker-compose build`

``docker-compose run --rm --user `id -u`:`id -g` composer install``

`docker-compose up -d`

`docker-compose exec php php /var/www/html/artisan migrate`

O status do servidor estará acessivel em http://localhost:3000

Os endpoints deverão ser testados usando o prefixo /api/. Por exemplo:

http://localhost:3000/api/tools
http://localhost:3000/api/tools/1

## Documentação

Disponível em http://localhost:3000/api/docs. escrita utilizando a sintaxe do **API Blueprint**. A visualização em HTML foi gerada utilizando o parser **Aglio**.

## Testes

Para rodar os testes, primeiro é necessário rodar as migrations do ambiente de testes

`docker-compose exec php php /var/www/html/artisan migrate --env=testing`

Em seguida, basta executar o PHPUnit no container correspondente

``docker-compose exec php /var/www/html/vendor/bin/phpunit``
