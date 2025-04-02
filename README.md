
# Guia de Estudos - Aplicação

Este repositório contém uma aplicação de guia de estudos com funcionalidades de gerenciamento de estudos, dashboard e sugestões.

## Pré-requisitos

Antes de rodar os comandos, certifique-se de que o Docker e o Docker Compose estão instalados no seu sistema. Você pode verificar se eles estão instalados com os seguintes comandos:

```bash
docker --version
docker-compose --version
```

## Rodando a Aplicação

1. Clone este repositório:
   ```bash
   git clone https://github.com/abrunaanunes/infnet-guia.git
   cd infnet-guia

2. Configuração do Ambiente
Antes de rodar a aplicação, copie o arquivo .env.example para .env e configure as variáveis de ambiente conforme necessário.
    ```bash
    cp .env.example .env

Edite o arquivo .env para ajustar as variáveis de ambiente de acordo com suas configurações. Aqui estão os valores recomendados para os ambientes de desenvolvimento e produção:

- Para desenvolvimento, configure o NODE_ENV como development.
- Para produção, configure o NODE_ENV como production.

3. Construa o ambiente Docker (Observação: remova o `--frozen-lockfile` na linha 10 do Dockerfile caso não tenha executado o `pnpm install` fora do container)
    ```bash
    docker-compose up --build

### Parâmetros Importantes

- **`--env-file .env`**: Especifica o arquivo `.env` que contém as variáveis de ambiente a serem usadas no Docker Compose.
- **`--build`**: Força a reconstrução das imagens do Docker antes de iniciar os containers.

### Acessando a Aplicação

Após iniciar a aplicação, você poderá acessá-la pelo endereço configurado em `APP_URL` no arquivo `.env` (por padrão, será `http://localhost:3000` para desenvolvimento).

### Outras Configurações

Se você precisar ajustar mais configurações, como a base de dados ou outras dependências, essas variáveis devem ser definidas no arquivo `.env` conforme a documentação dos serviços utilizados.

## Publicar imagem no DockerHub

1. Fazer login no Docker Hub
   ```bash
   docker login
   
2. Pelo terminal, na pasta do seu projeto, execute (lembre do . ou caminho do Dockerfile)
   ```bash
   docker build -t {nome-imagem} .

3. Coloque a tag da imagem
   ```bash
   docker tag {nome-imagem} {usuario-dockerhub}/{nome-imagem}p:latest

4. Enviar a imagem para o Docker Hub
   ```bash
   docker push {nome-usuario}/{nome-imagem}:latest
