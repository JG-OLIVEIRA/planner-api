# Planner API

## Descrição

API para planejamento de viagens, permitindo criar e atualizar viagens, convidar participantes, cadastrar atividades e links úteis e confirmar a participação dos convidados.

## Funcionalidades

- Criação, consulta, atualização e confirmação de viagens
- Convite e confirmação de participantes
- Cadastro e consulta de atividades da viagem
- Cadastro e consulta de links da viagem
- Validação das datas de início e término da viagem e das atividades
- Persistência com JPA e migrações versionadas com Flyway
- Console H2 habilitado para desenvolvimento local

## Tecnologias

- **Spring Framework** — Injeção de Dependências, Beans e Configurações
- **Spring Boot** — Autoconfiguração e execução da aplicação
- **Spring Web** — API REST e Controllers
- **Spring Data JPA** — Persistência e repositórios relacionais
- **Flyway** — Controle de migrações do banco de dados
- **H2** — Banco em memória para desenvolvimento local
- **MySQL e PostgreSQL** — Drivers disponíveis para ambientes relacionais
- **Hibernate Validator** — Validação de dados
- **Lombok** — Redução de código repetitivo

## Pré-requisitos

- Java Development Kit (JDK) 21 ou mais recente
- Maven
- Postman ou outra ferramenta para testar APIs REST

## Execução

Para executar a API:

```bash
./mvnw spring-boot:run
```

A aplicação usa H2 em memória com as configurações atuais. O console H2 fica disponível em `http://localhost:8080/h2-console`.

## Principais endpoints

- `POST /trips` — Cria uma viagem
- `GET /trips/{id}` — Consulta uma viagem
- `PUT /trips/{id}` — Atualiza uma viagem
- `GET /trips/{id}/confirm` — Confirma uma viagem e seus participantes
- `POST /trips/{id}/activities` e `GET /trips/{id}/activities` — Gerencia atividades
- `GET /trips/{id}/participants` — Lista participantes
- `POST /trips/{id}/invite` — Convida um participante
- `POST /participants/{id}/confirm` — Confirma um participante
- `POST /trips/{id}/links` e `GET /trips/{id}/links` — Gerencia links
