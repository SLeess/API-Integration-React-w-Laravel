# Sistema de Gerenciamento de Editais - ProCEAD/Unimontes

Este projeto é um sistema web completo para a publicação e gerenciamento de processos seletivos (editais) do CEAD/Unimontes. Ele é composto por uma API RESTful robusta construída com Laravel e um frontend reativo desenvolvido com React.

A aplicação permite que candidatos visualizem e se inscrevam nos editais, enquanto administradores gerenciam os processos seletivos através de um sistema granular de papéis e permissões.

## ✨ Funcionalidades Principais

  - **Autenticação Segura:** Sistema de login para Candidatos e Administradores utilizando Laravel Sanctum para comunicação SPA.
  - **Gerenciamento de Papéis e Permissões:** Controle de acesso robusto com o pacote `spatie/laravel-permission`, definindo papéis como `Super-Admin`, `Admin-Edital` e `Candidato`.
  - **Listagem e Detalhes de Editais:** Os usuários podem visualizar todos os editais ativos e seus detalhes. (EM ANDAMENTO)
  - **Inscrição de Candidatos:** Candidatos podem se inscrever nos editais para os quais têm permissão. (EM ANDAMENTO)
  - **Painel do Candidato:** Área exclusiva para o candidato acompanhar o status de suas inscrições.
  - **Painel Administrativo:** Área para administradores gerenciarem os editais e as inscrições.
  - **API RESTful:** Backend desacoplado que serve dados de forma segura para o frontend.  (EM ANDAMENTO)

## 🛠️ Tecnologias Utilizadas

### Backend (API)

  - **PHP 8.1+**
  - **Laravel 10+**
  - **Laravel Sanctum:** Para autenticação de SPA.
  - **Spatie Laravel Permission:** Para gerenciamento de papéis e permissões.
  - **MySQL / PostgreSQL:** Como banco de dados.

### Frontend

  - **React 18+**
  - **TypeScript**
  - **Vite:** Como ferramenta de build e servidor de desenvolvimento.
  - **Tailwind CSS:** Para estilização.
  - **React Router:** Para gerenciamento de rotas.
  - **Axios:** Para requisições à API.

## ⚙️ Pré-requisitos

Antes de começar, garanta que você tenha os seguintes softwares instalados na sua máquina:

  - [PHP](https://www.php.net/) (versão 8.1 ou superior)
  - [Composer](https://getcomposer.org/)
  - [Node.js](https://nodejs.org/) (versão 18 ou superior) e npm
  - Um servidor de banco de dados (MySQL, MariaDB ou PostgreSQL)

## 🚀 Instalação e Configuração

Siga os passos abaixo para configurar o ambiente de desenvolvimento local.

### 1\. Backend (API Laravel)

Clone o repositório e configure o ambiente da API:

```bash
# 1. Clone o repositório
git clone https://seu-repositorio.git
cd seu-repositorio/backend # ou o nome da pasta da sua API

# 2. Instale as dependências do PHP
composer install

# 3. Crie o arquivo de ambiente
cp .env.example .env

# 4. Gere a chave da aplicação
php artisan key:generate

# 5. Configure o arquivo .env com os dados do seu banco de dados (DB_DATABASE, DB_USERNAME, DB_PASSWORD)
# e configure as URLs para o frontend e a API.
# Exemplo de configuração crucial para Sanctum e CORS:
APP_URL=http://localhost:8000
SANCTUM_STATEFUL_DOMAINS=localhost:5173
SESSION_DOMAIN=localhost
```

```bash
# 6. Rode as migrações e as seeders (para criar tabelas e permissões iniciais)
php artisan migrate --seed

# 7. Crie o link simbólico para o armazenamento de arquivos
php artisan storage:link
```

### 2\. Frontend (Aplicação React)

Em um novo terminal, navegue para a pasta do frontend e configure o ambiente:

```bash
# 1. Navegue para a pasta do frontend
cd ../frontend # ou o nome da pasta do seu React App

# 2. Instale as dependências do JavaScript
npm install

# 3. Crie o arquivo de ambiente para o frontend
cp .env.example .env

# 4. Configure o arquivo .env.development.local (ou similar)
# Adicione a URL base da sua API Laravel.
VITE_API_BASE_URL=http://localhost:8000
```

## ▶️ Rodando a Aplicação

Para rodar a aplicação, você precisará de **dois terminais abertos simultaneamente**.

**Terminal 1: Iniciar o servidor da API Laravel**

```bash
# Na pasta do backend
php artisan serve
```

O servidor da API estará rodando em `http://localhost:8000`.

**Terminal 2: Iniciar o servidor de desenvolvimento do React**

```bash
# Na pasta do frontend
npm run dev
```

A aplicação React estará acessível em `http://localhost:5173` (ou a porta que o Vite indicar).

## 📝 Comandos Úteis

  - **Resetar o banco de dados e rodar as seeders:**

    ```bash
    php artisan migrate:fresh --seed
    ```

  - **Limpar o cache de permissões do Spatie (importante após criar novas permissões):**

    ```bash
    php artisan permission:cache-reset
    ```

  - **Limpar caches gerais do Laravel:**

    ```bash
    php artisan optimize:clear
    ```

  - **Rodar os testes do frontend:**

    ```bash
    npm test
    ```

  - **Gerar a build de produção do frontend:**

    ```bash
    npm run build
    ```

## 📚 Documentação da API (Opcional)

A documentação dos endpoints da API pode ser encontrada [aqui](https://www.google.com/). (EM ANDAMENTO).

-----
