# MongoDB User-Post API

Este projeto é uma API RESTful desenvolvida com Spring Boot, utilizando MongoDB como banco de dados. A aplicação implementa operações CRUD para entidades **User** e **Post**, além de consultas customizadas.

---

## 🚀 Funcionalidades

### Endpoints para **User**:
- **GET /users**: Lista todos os usuários.
- **GET /users/{id}**: Retorna um usuário por ID.
- **POST /users**: Insere um novo usuário.
- **DELETE /users/{id}**: Remove um usuário por ID.
- **PUT /users/{id}**: Atualiza as informações de um usuário.
- **GET /users/{id}/posts**: Lista os posts associados a um usuário.

### Endpoints para **Post**:
- **GET /posts/{id}**: Retorna um post por ID.
- **GET /posts/search**: Consulta posts com base em critérios personalizados (título, corpo, comentários e intervalo de datas).

---

## 🛠️ Tecnologias Utilizadas

- **Java 17**: Linguagem de programação principal.
- **Spring Boot 2.x**: Framework para desenvolvimento backend.
- **MongoDB**: Banco de dados NoSQL.
- **MongoDB Compass**: Ferramenta gráfica para gerenciar o MongoDB.
- **Spring Data MongoDB**: Integração com o banco de dados.
- **Maven**: Gerenciador de dependências e build.
- **Postman**: Para testar Endpoints.

---

## 💾 Configuração e Execução

1. **Pré-requisitos**:
   - [Java 17+](https://www.oracle.com/java/technologies/javase-jdk17-downloads.html)
   - [Maven](https://maven.apache.org/)
   - [MongoDB](https://www.mongodb.com/try/download/community)

2. **Configuração do Banco de Dados**:
   - Execute o MongoDB localmente (`mongod`).
   - Use o [MongoDB Compass](https://www.mongodb.com/products/compass) para criar:
     - Base de dados: `workshop_mongo`
     - Coleção: `user`

3. **Configuração da Aplicação**:
   - Configure a conexão com o MongoDB no arquivo `application.properties`:
     ```properties
     spring.data.mongodb.uri=mongodb://localhost:27017/workshop_mongo
     ```

4. **Execução do Projeto**:
   - Clone o repositório:
     ```bash
     git clone https:https://github.com/luixsouza/MongoDB_User_Post_API.git
     ```
   - Acesse o diretório do projeto:
     ```bash
     cd MongoDB_User_Post_API
     ```
   - Compile e execute:
     ```bash
     mvn spring-boot:run
     ```

5. **Testar Endpoints**:
   - Utilize ferramentas como **Postman** ou **cURL** para testar os endpoints REST.

---

## 📂 Dados de Instanciação

Durante a inicialização, alguns dados são inseridos automaticamente no banco:
- **Users**:
  - Maria Brown
  - Alex Green
  - Bob Grey
- **Posts**: Associados aos usuários acima, com comentários.

---

## ✨ Recursos Avançados

- **DTO (Data Transfer Object)**: Para otimizar o tráfego de dados e personalizar as respostas das APIs.
- **Consultas Customizadas**:
  - Busca por string no título.
  - Busca com múltiplos critérios (título, corpo, comentários, intervalo de datas).
- **Tratamento de Exceções**: Mensagens de erro padronizadas com `StandardError` e `ResourceExceptionHandler`.