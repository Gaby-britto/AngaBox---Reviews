# Entendendo decisões arquiteturais e a estrutura do projeto

### Como usar?

- Após rodar o projeto você pode alterar os arquivos da pasta `/apiAnGaBox`

### Estrutura do Projeto da API

- `./node_modules`: Diretório onde todas as dependências do projeto são armazenadas. Este diretório é gerenciado pelo npm e contém todos os pacotes necessários para a aplicação funcionar.

- `./src`: Diretório principal para o código-fonte da aplicação, onde a lógica e os componentes da API são implementados.
  - `./src/config`: Contém configurações importantes para o projeto. 
    - `./src/database.js`: Em vez de simular uma base de dados com JSON, esse arquivo passa a gerenciar a conexão com o MongoDB. Ele é essencial para configurar e manter a conexão com o banco de dados.
  - `./src/controller`: Diretório onde estão os controladores que lidam com as requisições HTTP.
    - `./src/controller/AdminController.js`: Controlador para operações relacionadas ao admin.
    - `./src/controller/UserController.js`: Controlador para operações relacionadas a usuários.
    - `./src/controller/PostController.js`: Controlador para operações relacionadas aos posts.
    - `./src/controller/MovieController.js`: Controlador para operações relacionadas aos filmes.
  
  - `./src/middlewares`: Diretório onde estão os middlewares da aplicação.
    - `./src/middlewares/validateAdmin.js`: Middleware para autenticação de admins.
    - `./src/middlewares/validateUser.js`: Middleware para autenticação de usuários.
  
  - `./src/routes`: Diretório onde estão definidas as rotas da API.
    - `./src/routes/admRouter.js`: Define rotas específicas para operações relacionadas a administradores.
      -  `'/' getAll`
      -  `'/:id' getOne` 
      -  `'/' create` 
      -  `'/' upate` 
      -  `'/:id' delete` 
  
    - `./src/routes/movieRouter.js`: Define rotas específicas para operações relacionadas aos movies.
         -  `'/' getAll`
      -  `'/:id' getOne` 
      -  `'/' create` 
      -  `'/' upate` 
      -  `'/:id' delete` 
  
    - `./src/routes/postRouter.js`: Define rotas específicas para operações relacionadas aos posts.
      -  `'/' getAll`
      -  `'/:id' getOne` 
      -  `'/' create`
      -  `'/:id' delete` 
  
    - `./src/routes/userRouter.js`: Define rotas específicas para operações relacionadas a usuários.
      -  `'/' getAll`
      -  `'/:id' getOne` 
      -  `'/' create` 
      -  `'/' upate` 
      -  `'/:id' delete` 
    - `./src/routes/router.js`: Arquivo que define as rotas da API e associa cada rota ao seu respectivo controlador.
      -  `'/user' userRoutes`
      -  `'/post' postRouter` 
      -  `'/movie' movieRouter` 
      -  `'/adm' admRouter` 
      -  `'/login'`
      -  
 - `./src/models`: Representa as entidades do sistema e define como os dados serão manipulados.
    - `./src/models/Admin.js`: Modelo que define a estrutura de dados dos administradores.
    - `./src/models/User.js`: Modelo que define a estrutura de dados dos usuários.
    - `./src/models/Post.js`: Modelo que define como os posts de resenha são estruturados.
    - `./src/models/Movie.js`: Modelo para manipulação dos dados de filmes. 

- `.env`:Contém variáveis de ambiente, como chaves secretas e configurações de conexão com banco de dados. Importante manter seguro e fora de controle de versão. 
- `.gitignore`: Lista os arquivos e diretórios que não devem ser incluídos no repositório Git, como node_modules e .env. 
- `./package-lock.json`: Arquivo que registra as versões exatas das dependências instaladas para garantir a consistência nas instalações.
- `./index.js`: Arquivo de entrada principal da aplicação.
- `./package.json`: Arquivo que gerencia as dependências do projeto e scripts, além de armazenar informações sobre o projeto.
