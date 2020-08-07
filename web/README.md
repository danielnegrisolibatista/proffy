
# Projeto Web

## Iniciando o projeto Web

- Yarn

`yarn create react-app web --template typescript`

- NPM

`npx create-react-app web --template typescript`

### Ajustando os arquivos do projeto

- Readme: Excluir o arquivo
- src/index.css: Excluir o arquivo
- src/App.css: Excluir o arquivo
- src/App.test.txs: Excluir o arquivo
- src/logo.svg: Excluir o arquivo
- src/serviceWorker: Excluir o arquivo
- src/setupTests.ts: Excluir o arquivo
- public: Remover todos os arquivos menos o index.html
- src/App.tsx: Limpar os imports que não serão usados
- src/index.tsx: Limpar os imports que não serão usados
- public/index.html: Limpar os imports que não serão usados

### Conceitos importantes

- div.root: Onde é injetado a aplicação
- JSX: Html dentro do JS
- Componentes: Forma de isolar códigos repetitivos

### Configurando imagens, estilos e fontes

- Criar as pastas assets/images, assets/styles/global.css
- Criar o arquivo global.css e os estilos
- Selecionar a origem das fontes Archivo (400, 700) e Poppins (400)
- Incluir o caminho da fonte no arquivo public/index.html
- Incluir o import do arquivo css no App.tsx `import './assets/styles/global.css'`

### Criando a Landing Page

- Criar as pastas/arquivos pages/Landing/index.tsx
- Incluir o import do componente Landing no App.tsx `import Landing from './pages/Landing';'`
- Criar o css da Landing Page

### Roteamento

- Instalar o react-router-dom `yarn add react-router-dom`
- Instalar a tipagem do react-router-dom `yarn add @types\react-router-dom -D`
- Criar o arquivo src/routes.tsx
- Incluir o Routes no arquivo App.tsx
- Remover o Landing do arquivo App.tsx

- No arquivo Landing/index.jsx, incluir o import `import { Link } from 'react-router-dom';`
- No arquivo Landing/index.jsx, alterar o elemento `<a />` para `<Link to="/rota">`

### Criando a TeacherForm

- Criar as pastas/arquivos pages/TeacherForm/index.tsx e pages/TeacherForm/styles.css

### Criando a TeacherList

- Criar as pastas/arquivos pages/TeacherList/index.tsx e pages/TeacherList/styles.css

### Criando o PageHeader

- Criar as pastas/arquivos src/components/PageHeader/index.tsx e src/components/PageHeader/styles.css

#### Aprendendo sobre propriedades e Children

### Dicas CSS

- font-size: controle do tamanho da fonte
- rem: permitir aumentar e diminuir o tamanho da fonte de acordo com o font-size
