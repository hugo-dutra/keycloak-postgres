# 🛡️ Keycloak com Postgres - Docker Compose

## 📋 Visão Geral
Este projeto utiliza 🐳 Docker Compose para orquestrar a execução de dois serviços:
1. `keycloak` - Um sistema de gerenciamento de identidades e acessos.
2. `postgres` - Banco de dados relacional utilizado pelo Keycloak.

## ✅ Pré-requisitos
- Docker 🐳 e Docker Compose instalados.
- Conhecimento básico em Docker e gerenciamento de containers.

## 🚀 Configuração

### Serviços Definidos

#### Keycloak
- Imagem: `quay.io/keycloak/keycloak:legacy`
- Porta: `8080`
- Dependências: `postgres`
- Variáveis de ambiente: (nunca deixe hardcoded em produção)
  - `DB_VENDOR: POSTGRES`
  - `DB_ADDR: postgres`
  - `DB_DATABASE: keycloak`
  - `DB_USER: keycloak`
  - `DB_SCHEMA: keycloak_schema`
  - `DB_PASSWORD: keycloak`
  - `DB_PORT: 5432`
  - `KEYCLOAK_USER: admin`
  - `KEYCLOAK_PASSWORD: admin`

#### Postgres
- Imagem: `postgres`
- Porta: `5432`
- Volumes:
  - Local: `D:/curso_spring_db`
  - Docker: `/var/lib/postgresql/data`
  - Init script: `./init-schema.sql`
- Variáveis de ambiente: (nunca deixe hardcoded em produção)
  - `POSTGRES_DB: keycloak`
  - `POSTGRES_USER: keycloak`
  - `POSTGRES_PASSWORD: keycloak`

## 🚨 Atenção
Não se esqueça de alterar as credenciais e outras informações sensíveis antes de utilizar em um ambiente de produção!

## 📝 Como Usar
1. Clone o repositório ou copie o `docker-compose.yml`.
2. No terminal, navegue até o diretório do arquivo.
3. Execute o comando: `docker-compose up`.
4. Acesse o Keycloak em `http://localhost:8080`.

## 📚 Recursos Adicionais
- [Documentação do Keycloak](https://www.keycloak.org/documentation.html)
- [Documentação do Postgres](https://www.postgresql.org/docs/)
- [Documentação do Docker Compose](https://docs.docker.com/compose/)

---

Copie e cole este texto no seu `README.md` no GitHub para uma exibição elegante e informativa!
