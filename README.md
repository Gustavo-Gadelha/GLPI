# GLPI

Sistema de gerenciamento de ativos e helpdesk rodando em containers Docker.

## Estrutura

- **glpi** — container com a aplicação GLPI
- **mysql** — container com MySQL 9.7.0 na porta padrão `3306`

As credenciais do banco de dados são definidas no arquivo `.env`. Use o `.env.example` como referência para configurar as variáveis de ambiente. O host do banco de dados é `mysql` por padrão.

O **Ngrok** é utilizado para expor o container externamente durante a apresentação, utilizando a porta HTTP `80`.

## Pré-requisitos

- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [Ngrok](https://open.docker.com/extensions/marketplace?extensionId=ngrok/ngrok-docker-extension) (extensão do Docker Desktop — recomendado)

> [!TIP]
> Instale o Ngrok diretamente pelo Docker Desktop em **Extensions → Browse → Ngrok**. Isso evita instalar o CLI separadamente e permite gerenciar os túneis pela interface gráfica.

## Configuração

Copie o arquivo de exemplo e preencha com suas credenciais:

```bash
# Windows
copy .env.example .env

# Linux/macOS
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

## Acesso Locamente

| Serviço | URL                |
|---------|--------------------|
| GLPI    | <http://localhost> |

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

Para expor o GLPI externamente durante a apresentação, utilize a extensão do Ngrok no Docker Desktop:

1. Abra o **Docker Desktop**
2. Acesse a aba **Extensions** no menu lateral
3. Abra o **Ngrok**
4. Crie um túnel apontando para a porta `80`
5. Compartilhe a URL pública gerada (ex: `https://xxxx.ngrok.io`)

Ou via CLI, caso prefira:

```bash
ngrok http 80
```

## CI/CD

O projeto utiliza GitHub Actions para validar automaticamente que os containers sobem e o GLPI está acessível a cada push ou pull request na branch main.

O workflow está em `.github/workflows/build.yml` e executa os seguintes passos:

1. Faz o checkout do repositório
2. Cria o `.env` a partir do `.env.example`
3. Valida e cria os containers com docker compose create (sem iniciá-los)
4. Em caso de falha, exibe os logs dos containers automaticamente
