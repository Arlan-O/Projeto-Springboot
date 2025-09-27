# API Rest com Spring Boot 

![Badge de Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)
![Badge da Linguagem](https://img.shields.io/badge/linguagem-Java-blue)
![Badge do Framework](https://img.shields.io/badge/framework-Spring%20Boot%203-green)

## 📖 Sobre o Projeto

Este projeto é uma API RESTful para uma clínica fictícia. A aplicação permite o gerenciamento completo (CRUD: Criar, Ler, Atualizar e Deletar) de **Médicos** e **Pacientes**.

Foi desenvolvido como um projeto de estudos com o auxílio de um professor, aplicando as melhores práticas de desenvolvimento de APIs com Spring Boot, como o uso de DTOs (Data Transfer Objects) para a troca de informações, o padrão Repository para acesso ao banco de dados e a separação de responsabilidades em Controllers.

---

## 🛠️ Tecnologias Utilizadas

As seguintes ferramentas e tecnologias foram usadas na construção do projeto:

- **[Java 17](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html)**
- **[Spring Boot 3](https://spring.io/projects/spring-boot)**
- **[Spring Data JPA](https://spring.io/projects/spring-data-jpa)**
- **[Maven](https://maven.apache.org/)** para gerenciamento de dependências
- **[H2 Database](https://www.h2database.com/html/main.html)** como banco de dados em memória para desenvolvimento
- **[Postman](https://www.postman.com/)** para testes e documentação dos endpoints

---

## 🚀 Como Começar

Siga as instruções abaixo para executar o projeto em sua máquina local.

### Pré-requisitos

Antes de começar, você vai precisar ter as seguintes ferramentas instaladas em sua máquina:
- [Git](https://git-scm.com)
- [JDK 17 ou superior](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html)
- [Maven](https://maven.apache.org/)
- Uma IDE de sua preferência, como [IntelliJ IDEA](https://www.jetbrains.com/idea/) ou [VS Code](https://code.visualstudio.com/).

### Clonando o Repositório

```bash
git clone [https://URL-DO-SEU-REPOSITORIO-AQUI.git](https://URL-DO-SEU-REPOSITORIO-AQUI.git)
```

### Executando a Aplicação

1.  Abra o projeto na sua IDE.
2.  Aguarde o Maven baixar todas as dependências do projeto.
3.  Execute a classe principal `SenacApplication` que contém a anotação `@SpringBootApplication`.
4.  A API estará disponível para ser acessada em `http://localhost:8080`.

---

## Endpoints da API

A API oferece os seguintes endpoints para manipulação dos dados.

### 👩‍⚕️ Médicos

#### `POST /medicos`

Cria (cadastra) um novo médico. A especialidade deve ser uma das seguintes: `ORTOPEDIA`, `CARDIOLOGIA`, `GINECOLOGIA`, `DERMATOLOGIA`.

**Request Body:**
```json
{
  "nome": "Nome do Médico",
  "email": "medico@voll.med",
  "crm": "123456",
  "especialidade": "CARDIOLOGIA",
  "endereco": {
    "logradouro": "Rua Exemplo",
    "bairro": "Bairro Modelo",
    "cep": "12345678",
    "cidade": "Cidade Exemplo",
    "uf": "SP",
    "numero": "100",
    "complemento": "Sala 2"
  }
}
```
**Response:** `201 Created`

---
#### `GET /medicos`

Lista todos os médicos cadastrados de forma paginada.

**Response:** `200 OK`
```json
[
    {
        "id": 1,
        "nome": "Nome do Médico",
        "email": "medico@voll.med",
        "crm": "123456",
        "especialidade": "CARDIOLOGIA"
    }
]
```

---
#### `PUT /medicos`

Atualiza os dados de um médico existente. O `id` do médico deve ser incluído no corpo da requisição.

**Request Body:**
```json
{
  "id": 1,
  "nome": "Nome do Médico Atualizado",
  "telefone": "11999998888",
  "endereco": {
    "logradouro": "Rua Nova",
    "bairro": "Bairro Novo",
    "cep": "87654321",
    "cidade": "Cidade Nova",
    "uf": "RJ",
    "numero": "200",
    "complemento": "Sala 3"
  }
}
```
**Response:** `200 OK`

---
#### `DELETE /medicos/{id}`

Exclui logicamente um médico pelo seu `id`. (O registro é marcado como inativo, não removido do banco).

**Exemplo de URL:**
```
http://localhost:8080/medicos/1
```
**Response:** `204 No Content`

---

### 🤒 Pacientes

#### `POST /pacientes`

Cria um novo registro de paciente.

**Request Body:**
```json
{
  "nome": "Arlan Henrique Pires de Oliveira",
  "email": "arlan@gmail.com",
  "cpf": "0000000000",
  "telefone": "11111111111",
  "endereco": {
    "logradouro": "Rua 7",
    "bairro": "Vila St Antonio",
    "cep": "12345688",
    "cidade": "Maringa",
    "uf": "PR",
    "numero": "7777",
    "complemento": "complemento"
  }
}
```
**Response:** `201 Created`

---
#### `GET /pacientes`

Lista todos os pacientes cadastrados.

**Response:** `200 OK`
```json
[
  {
    "id": 1,
    "nome": "Arlan Henrique Pires de Oliveira",
    "email": "arlan@gmail.com",
    "cpf": "0000000000"
  }
]
```

---
#### `PUT /pacientes`

Atualiza os dados de um paciente existente. O `id` do paciente deve ser incluído no corpo da requisição.

**Request Body:**
```json
{
  "id": 1,
  "nome": "Arlan Henrique Oliveira",
  "telefone": "1559999",
  "endereco": {
    "logradouro": "Rua Nova",
    "bairro": "Vila St Antonio",
    "cep": "1654",
    "cidade": "Maringá",
    "uf": "PR",
    "numero": "7777",
    "complemento": "ap 107"
  }
}
```
**Response:** `200 OK`

---
#### `DELETE /pacientes/{id}`

Exclui um paciente pelo seu `id`.

**Exemplo de URL:**
```
http://localhost:8080/pacientes/9
```
**Response:** `204 No Content`

---

## Autor

**Arlan Henrique Pires de Oliveira**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/SEU-PERFIL-AQUI/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/SEU-USUARIO-AQUI)
