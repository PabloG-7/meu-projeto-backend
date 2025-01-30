# *UserFlow*

UserFlow é um projeto de backend desenvolvido com *Node.js* e *MySQL* para gerenciar usuários e comentários. Ele fornece uma API RESTful que permite criar, listar e gerenciar dados de forma simples e eficiente.

---

## *Funcionalidades*

- *Cadastro de Usuários*:
  - Crie novos usuários com nome e e-mail.
- *Listagem de Usuários*:
  - Obtenha uma lista de todos os usuários cadastrados.
- *Cadastro de Comentários*:
  - Permite que os usuários enviem comentários.
- *Listagem de Comentários*:
  - Exibe todos os comentários em ordem cronológica.

---

## *Tecnologias Utilizadas*

- *Node.js*: Ambiente de execução JavaScript.
- *Express*: Framework para criar a API.
- *MySQL*: Banco de dados para armazenar usuários e comentários.
- *Dotenv*: Gerenciamento de variáveis de ambiente.
- *Cors*: Permite requisições de diferentes origens.

---
2. Navegue até a pasta do projeto:
   cd userflow
   
3. Instale as dependências:
   npm install
   

### *Configuração*
1. Crie um arquivo .env na raiz do projeto e configure as variáveis de ambiente:
   
   DB_HOST=localhost
   DB_USER=root
   DB_PASSWORD=sua_senha
   DB_NAME=userflow
   PORT=3000
   
2. Execute o script SQL para criar as tabelas no MySQL:
3. 
   CREATE TABLE users (
     id INT AUTO_INCREMENT PRIMARY KEY,
     name VARCHAR(255) NOT NULL,
     email VARCHAR(255) NOT NULL UNIQUE
   );

   CREATE TABLE comments (
     id INT AUTO_INCREMENT PRIMARY KEY,
     name VARCHAR(255) NOT NULL,
     comment TEXT NOT NULL,
     created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );
   

### *Executando o Projeto*
1. Inicie o servidor: 
   npm start
   
2. Acesse a API em http://localhost:3000.

---

## *Endpoints da API*

### *Usuários*
- **GET /api/users**: Lista todos os usuários.
- **POST /api/users**: Cria um novo usuário.

### *Comentários*
- **GET /api/comments**: Lista todos os comentários.
- **POST /api/comments**: Cria um novo comentário.

---

## *Exemplos de Requisições*

### *Criar Usuário*
- *Requisição*:
  
  POST /api/users
  
  json
  {
    "name": "João",
    "email": "joao@example.com"
  }
  

- *Resposta*:
  json
  {
    "id": 1,
    "name": "João",
    "email": "joao@example.com"
  }
  

### *Criar Comentário*
- *Requisição*:
  bash
  POST /api/comments
  
  json
  {
    "name": "Maria",
    "comment": "Adorei o projeto!"
  }
  

- *Resposta*:
  json
  {
    "id": 1,
    "name": "Maria",
    "comment": "Adorei o projeto!",
    "created_at": "2023-10-05T12:34:56.000Z"
  }
  
---

## *Licença*

Este projeto está licenciado sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
