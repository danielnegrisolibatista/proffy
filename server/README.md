
# Projeto Server

## Iniciando o projeto Server

- Yarn

`yarn init -y`

- NPM

`npm init -y`

## Adicionando o Typescript

- Yarn

`yarn add typescript -D`

- NPM

`npm install typescript -D`

## Iniciando a configuração do Typescript

- Yarn

`yarn tsc --init`

- NPM

`npx tsc --init`

- Alterar no arquivo tsconfig.json de `"target": "es5"` para `"target": "es2017"`
- Instalar a dependência `yarn add ts-node-dev -D` para atualizar o servidor a cada alteração nos arquivos

### Ajustando os arquivos do projeto

- Adicionar o script de start no arquivo package.json `ts-node-dev --transpile-only --ignore-watch --respawn src/server.ts`
- Criar a pasta/arquivo src/server.ts

### Instalando outras dependências

- Adicionar o express `yarn add express`
- Adicionar a tipagem do express `yarn add @types/express -D`
- Adicionar o sqllite `yarn add knex sqlite3`
- Adiionar o CORS `yarn add cors`
- Adicionar a tipagem do CORS `yarn add @types/cors -D`

### Criando a conexão com o banco de dados e as tabelas

- Criar a pasta/arquivo src/database/connection.ts
- Criar o arquivo de configuração ./knexfile.js
- Criar a pasta/arquivo src/database/migrations
- Criar as migrations

### Roteamento e Controlles

- Criar os controllers `ConnectionsController` e `ClassesController`
- Alterar o routes.ts para utilizar os controllers
