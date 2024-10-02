## Modelo de Documentação de API

### Contexto 
A documentação de API é o documento que reúne as principais especificações técnicas que você precis saber para realizar uma requisição e obter uma resposta sucesso em uma integração com APIs. No caso de APIs construídas a partir de uma arquitetura REST, é comum que se use a especificação OpenAPI para documentar os endpoints, semelhante ao que se encontra no modelo de API do [Swagger](https://petstore.swagger.io/#/), principal ferramenta do mercado usada para documentar APIs deste tipo. 

## Exemplo de documentação 
# Documentação de API da Intelligenza
### Introdução
A API da Intelligenza permite que desenvolvedores integrem e interajam com os serviços oferecidos pela nossa plataforma. Esta documentação fornece informações sobre como usar a API, incluindo endpoints, métodos, parâmetros e exemplos de requisições e respostas.

## Autenticação
Para acessar a API, você precisará de um token de autenticação. Este token deve ser incluído no cabeçalho de cada requisição.

## Endpoints
1. **Criar Usuário**
Endpoint: /api/v1/usuarios
Método: POST
Descrição: Cria um novo usuário na plataforma.

### Parâmetros do Corpo da Requisição:
```bash
{
  "nome": "string",
  "email": "string",
  "senha": "string",
  "telefone": "string"
}
```
### Resposta Sucesso:
```
{
  "mensagem": "Usuário criado com sucesso.",
  "usuario": {
    "id": "integer",
    "nome": "string",
    "email": "string",
    "telefone": "string"
  }
}
```
### Código de Status:
- 201 Created: Usuário criado com sucesso.
- 400 Bad Request: Dados inválidos.

## 2. Listar Usuários
Endpoint: /api/v1/usuarios
Método: GET
Descrição: Retorna uma lista de todos os usuários.

### Parâmetros de Consulta:

- pagina: (opcional) número da página para paginação.
- limite: (opcional) número máximo de usuários por página.
- 
### Resposta Sucesso:
```bash
{
  "usuarios": [
    {
      "id": "integer",
      "nome": "string",
      "email": "string",
      "telefone": "string"
    }
  ],
  "paginaAtual": "integer",
  "totalPaginas": "integer"
}
```
### Código de Status:
- 200 OK: Lista de usuários retornada com sucesso.

## 3. Atualizar Usuário
Endpoint: /api/v1/usuarios/{id}
Método: PUT
Descrição: Atualiza os dados de um usuário específico.

### Parâmetros do Corpo da Requisição:
```bash
{
  "nome": "string",
  "email": "string",
  "telefone": "string"
}
```
### Resposta Sucesso:
```bash
{
  "mensagem": "Usuário atualizado com sucesso.",
  "usuario": {
    "id": "integer",
    "nome": "string",
    "email": "string",
    "telefone": "string"
  }
}
```
### Código de Status:
- 200 OK: Usuário atualizado com sucesso.
- 404 Not Found: Usuário não encontrado.

## 4. Deletar Usuário
Endpoint: /api/v1/usuarios/{id}
Método: DELETE
Descrição: Remove um usuário da plataforma.

### Resposta Sucesso:
```bash
{
  "mensagem": "Usuário removido com sucesso."
}
```
### Código de Status:
- 204 No Content: Usuário deletado com sucesso.
- 404 Not Found: Usuário não encontrado.

## Tratamento de Erros
A API da Intelligenza retornará mensagens de erro claras para ajudar a diagnosticar problemas. Aqui estão alguns códigos de erro comuns:

- 400 Bad Request: A requisição não pôde ser processada devido a dados inválidos.
- 401 Unauthorized: O token de autenticação é inválido ou não foi fornecido.
- 404 Not Found: O recurso solicitado não foi encontrado.
- 500 Internal Server Error: Um erro inesperado ocorreu no servidor.
 
## Conclusão
Esta documentação fornece uma visão geral da API da Intelligenza, permitindo que você integre facilmente os serviços em suas aplicações. Para mais informações ou suporte adicional, entre em contato com a equipe de suporte da Intelligenza.
