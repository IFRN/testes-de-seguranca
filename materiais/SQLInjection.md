# SQL Injection - Guia Básico

## Introdução

SQL Injection é uma técnica de ataque que explora vulnerabilidades em aplicações web que interagem com bancos de dados SQL. O atacante insere ou "injeta" código SQL malicioso em uma consulta SQL através da entrada de dados da aplicação, com o objetivo de manipular ou acessar informações não autorizadas.

## Como Funciona

### 1. Entrada de Dados

A SQL Injection ocorre quando a aplicação não valida ou sanitiza adequadamente a entrada de dados do usuário. Por exemplo, um campo de login que aceita qualquer entrada sem verificação.

### 2. Construção da Consulta SQL

A aplicação constrói uma consulta SQL usando a entrada do usuário. Se a entrada não for tratada corretamente, o código SQL malicioso pode ser inserido.

#### Exemplo Vulnerável

```sql
SELECT * FROM users WHERE username = 'usuario' AND password = 'senha';
```

Se o atacante inserir `' OR '1'='1` como o nome de usuário, a consulta se torna:

```sql
SELECT * FROM users WHERE username = '' OR '1'='1' AND password = 'senha';
```

### 3. Execução da Consulta

O banco de dados executa a consulta modificada, que pode resultar em acesso não autorizado a dados, modificação de dados ou outras ações maliciosas.
