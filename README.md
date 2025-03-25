
# Guia de Estudos - Aplicação

Este repositório contém uma aplicação de guia de estudos com funcionalidades de gerenciamento de estudos, dashboard e sugestões.

## Requisitos

- Docker
- Docker Compose

## Rodando a Aplicação

1. Clone este repositório:
   ```bash
   git clone https://github.com/renanoliveiramentor/infnet-guia.git
   cd infnet-guia

2. Crie um arquivo .env a partir do .env.example:

    ```bash
    cp .env.example .env

3. Construa e inicie os contêineres com o Docker Compose:

    ```bash
    docker-compose up --build

4. Acesse a aplicação no navegador:

    ```bash
    http://localhost:3000