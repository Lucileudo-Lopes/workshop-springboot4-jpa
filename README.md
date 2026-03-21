📦 E-commerce API - Spring Boot
📌 Sobre o Projeto

Esta é uma API RESTful desenvolvida com Java e Spring Boot que simula um sistema completo de e-commerce.

A aplicação permite o gerenciamento de usuários, pedidos, produtos e categorias, incluindo relacionamentos complexos entre entidades e tratamento global de exceções, seguindo boas práticas de arquitetura em APIs REST.

🚀 Tecnologias Utilizadas
Java 25
Spring Boot
Spring Data JPA
H2 Database (ambiente de teste)
MySQL / PostgreSQL (produção)
Maven
Postman
🏗️ Arquitetura do Projeto

O sistema segue o padrão em camadas:

Entities → Modelos de domínio
Repositories → Acesso a dados com JPA
Services → Regras de negócio
Resources (Controllers) → Endpoints REST
Exceptions → Tratamento global de erros
🔗 Relacionamentos
User → Order → One-to-Many
Order → Payment → One-to-One
Product ↔ Category → Many-to-Many
Order ↔ Product (OrderItem) → Many-to-Many com atributos extras
⚙️ Como Executar o Projeto
🔹 1. Clonar repositório
git clone https://github.com/Lucileudo-Lopes/workshop-springboot4-jpa/edit/main/README.md
🔹 2. Configurar ambiente
🧪 Perfil de teste (H2)
spring.profiles.active=test
spring.jpa.open-in-view=true
🏭 Perfil de produção (MySQL/PostgreSQL)
spring.profiles.active=prod

spring.datasource.url=jdbc:mysql://localhost:3306/ecommerce
spring.datasource.username=seu_usuario
spring.datasource.password=sua_senha

spring.jpa.hibernate.ddl-auto=update
🔹 3. Executar aplicação
mvn spring-boot:run
📡 Endpoints da API
👤 Usuários
GET /users → Lista todos os usuários
GET /users/{id} → Busca usuário por ID
POST /users → Cria usuário
PUT /users/{id} → Atualiza usuário
DELETE /users/{id} → Remove usuário
📦 Pedidos
GET /orders
GET /orders/{id}
🛍️ Produtos
GET /products
GET /products/{id}
🏷️ Categorias
GET /categories
GET /categories/{id}
🧪 Exemplo de Requisição
➤ Criar usuário
POST /users
{
  "name": "Bob Brown",
  "email": "bob@gmail.com",
  "phone": "977557755",
  "password": "123456"
}
📥 Exemplo de Resposta
{
  "id": 1,
  "name": "Bob Brown",
  "email": "bob@gmail.com",
  "phone": "977557755"
}
⚠️ Tratamento de Exceções

A API possui tratamento global utilizando @ControllerAdvice:

ResourceNotFoundException → 404 Not Found
DatabaseException → 400 Bad Request
EntityNotFoundException → Erros de atualização
🧮 Regras de Negócio
Cálculo de subtotal por item do pedido
Cálculo do valor total do pedido
Associação automática entre entidades
📚 Aprendizados Aplicados
Estruturação de APIs REST com Spring Boot
Uso de JPA e mapeamento de entidades
Boas práticas de arquitetura em camadas
Tratamento global de exceções
Uso de perfis de ambiente (test/prod)
🔮 Melhorias Futuras
🔐 Autenticação e autorização com JWT
📄 Paginação e filtros
✅ Validação com Bean Validation
📊 Documentação com Swagger/OpenAPI
🐳 Docker para deploy
👨‍💻 Autor

Desenvolvido por Lucileudo
