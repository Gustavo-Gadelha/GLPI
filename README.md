# GLPI

Sistema de gerenciamento de ativos e helpdesk rodando em containers Docker.

## Estrutura

- **glpi** — container com a aplicação GLPI
- **mysql** — container com MySQL 9.7.0 na porta padrão `3306`

As credenciais do banco de dados são definidas no arquivo `.env`. Use o `.env.example` como referência para configurar as variáveis de ambiente. O host do banco de dados é `mysql` por padrão.

O **Ngrok** é utilizado para expor o container externamente durante a apresentação, utilizando a porta HTTP `80`.

## Pré-requisitos

- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [Ngrok](https://open.docker.com/extensions/marketplace?extensionId=ngrok/ngrok-docker-extension) (extensão do docker)

## Configuração

Copie o arquivo de exemplo e preencha com suas credenciais:

```bash
copy .env.example .env
```

ou no Linux

```bash
cp .env.example .env
```

## Comandos

Subir os containers:

```bash
docker compose up -d
```

Parar os containers e remover os volumes:

```bash
docker compose down -v
```

Visualizar os logs:

```bash
# Todos os containers
docker compose logs -f

# Apenas o GLPI
docker compose logs -f glpi

# Apenas o banco de dados
docker compose logs -f mysql
```

## Acesso

| Serviço | URL                     |
|---------|-------------------------|
| GLPI    | <http://localhost:8080> |

### Credenciais padrão do GLPI

> [!WARNING]
> Altere todas as senhas padrão após o primeiro acesso.

| Usuário     | Senha      | Perfil           |
|-------------|------------|------------------|
| `glpi`      | `glpi`     | Super-Admin      |
| `tech`      | `tech`     | Técnico          |
| `normal`    | `normal`   | Usuário normal   |
| `post-only` | `postonly` | Somente abertura |

## Apresentação com Ngrok

Para expor o GLPI externamente durante a apresentação:

```bash
ngrok http 8080
```

O Ngrok irá gerar uma URL pública (ex: `https://xxxx.ngrok.io`) para ser compartilhada.
