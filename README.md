# 🐾 ClyDay API

Sistema RESTful desenvolvido em Java + Spring Boot para gerenciamento de tutores, pets, medicações, atividades e ranking gamificado de cuidados com animais.

---

# 📌 Sobre o Projeto

O **ClyDay** é uma API desenvolvida com foco em organização e gamificação da rotina de cuidados com pets.

O sistema permite:

* cadastro de tutores
* cadastro de pets
* controle de medicações
* registro de atividades
* cálculo de streaks
* ranking semanal de pontuação
* documentação automática com Swagger

---

# 🚀 Tecnologias Utilizadas

* Java 21
* Spring Boot
* Spring Data JPA
* Hibernate
* Maven
* H2 Database
* Swagger/OpenAPI
* Bean Validation
* Cache
* Postman

---

# 🏗️ Arquitetura do Projeto

O projeto segue arquitetura em camadas:

```text
Controller → Service → Repository → Database
```

Separação utilizada:

```text
controller/
service/
repository/
entity/
dto/
config/
exception/
util/
```

---

# 📂 Estrutura do Projeto

```text
src/main/java/com/clyday/clyday_api

├── config
├── controller
├── dto
├── entity
├── exception
├── repository
├── service
├── util
└── ClydayApiApplication
```

---

# 📊 Funcionalidades

## 👤 Tutor

* cadastrar tutor
* listar tutores
* buscar tutor por ID
* deletar tutor
* busca por nome

---

## 🐶 Pet

* cadastrar pet
* listar pets
* buscar pet por ID
* deletar pet
* relacionamento com tutor

---

## 💊 Medicação

* cadastrar medicação
* listar medicações
* buscar medicação por ID
* deletar medicação
* relacionamento com pet

---

## 🏃 Atividades

* registrar atividades
* listar atividades
* calcular pontuação
* sistema de streak

---

## 🏆 Ranking

* ranking semanal
* cache de ranking
* soma de pontos por tutor

---

# 🔥 Funcionalidades Extras

✅ DTOs
✅ Bean Validation
✅ Exception Handler Global
✅ Cache
✅ Paginação
✅ Swagger
✅ Strategy Pattern
✅ Factory Pattern
✅ Relacionamentos JPA
✅ API RESTful

---

# 🧠 Design Patterns Utilizados

## Strategy Pattern

Utilizado para cálculo de pontuação.

```text
PontuacaoStrategy
```

---

## Factory Pattern

Responsável por retornar a estratégia correta de pontuação.

```text
PontuacaoFactory
```

---

# 🗄️ Relacionamentos

## Tutor → Pets

```text
1 Tutor possui vários Pets
```

## Pet → Medicações

```text
1 Pet possui várias Medicações
```

## Pet → Atividades

```text
1 Pet possui várias Atividades
```

---

# ⚙️ Como Executar o Projeto

## 1. Clone o projeto

```bash
git clone https://github.com/SEU-USUARIO/clyday-api.git
```

---

## 2. Abra no IntelliJ

Importe como projeto Maven.

---

## 3. Execute a aplicação

Execute:

```text
ClydayApiApplication.java
```

---

# 🌐 URLs Importantes

## Swagger

```text
http://localhost:8080/swagger-ui/index.html
```

## H2 Console

```text
http://localhost:8080/h2-console
```

---

# 📮 Endpoints Principais

## Tutor

```http
POST /tutores
GET /tutores
GET /tutores/{id}
DELETE /tutores/{id}
```

---

## Pet

```http
POST /pets
GET /pets
GET /pets/{id}
DELETE /pets/{id}
```

---

## Medicação

```http
POST /medicacoes
GET /medicacoes
GET /medicacoes/{id}
DELETE /medicacoes/{id}
```

---

## Atividade

```http
POST /atividades
GET /atividades
```

---

## Ranking

```http
GET /ranking
```

---

# 📑 Exemplo JSON

## Criar Tutor

```json
{
  "nome": "Giovana",
  "email": "giovana@email.com"
}
```

---

## Criar Pet

```json
{
  "nome": "Thor",
  "especie": "Cachorro",
  "idade": 3,
  "tutorId": 1
}
```

---

## Criar Medicação

```json
{
  "nome": "Antibiótico",
  "descricao": "Tomar após refeição",
  "obrigatoria": true,
  "petId": 1
}
```

---

## Criar Atividade

```json
{
  "tipo": "Passeio",
  "pontos": 20,
  "data": "2026-05-23",
  "petId": 1
}
```

---

# 🛡️ Tratamento de Erros

O projeto possui tratamento global de exceções utilizando:

```text
@RestControllerAdvice
```

Erros tratados:

* 400 BAD REQUEST
* 404 NOT FOUND
* 500 INTERNAL SERVER ERROR

---

# 📈 Cache

O ranking semanal utiliza cache para melhorar performance:

```text
@Cacheable("ranking")
```

---

# 👩‍💻 Desenvolvido por

**Giovana Souza Vieira**
Projeto acadêmico — ClyDay API 🐾

