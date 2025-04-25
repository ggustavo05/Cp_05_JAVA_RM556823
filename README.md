# CP 05 Deck Builder API - Magic: The Gathering


## 1. Início

Esta API tem como objetivo fornecer uma plataforma para construção e gerenciamento de decks de Magic: The Gathering (MTG). Ela permite criar, editar, buscar e excluir decks e cartas, além de oferecer funcionalidades adicionais como categorização por formato, busca avançada e importação/exportação de decks.

## 2. Rotas da API

| Método | Rota                            | Descrição                                       | Status Codes         |
|--------|----------------------------------|------------------------------------------------|----------------------|
| GET    | /decks                          | Listar todos os decks                          | 200, 500             |
| GET    | /decks/{id}                     | Buscar deck por ID                             | 200, 404, 500        |
| POST   | /decks                          | Criar novo deck                                | 201, 400, 500        |
| PUT    | /decks/{id}                     | Atualizar deck existente                       | 200, 400, 404, 500   |
| DELETE | /decks/{id}                     | Excluir deck existente                         | 204, 404, 500        |
| GET    | /cartas                         | Listar todas as cartas                         | 200, 500             |
| GET    | /cartas/{id}                    | Buscar carta por ID                            | 200, 404, 500        |
| POST   | /cartas                         | Criar nova carta                               | 201, 400, 500        |
| PUT    | /cartas/{id}                    | Atualizar carta existente                      | 200, 400, 404, 500   |
| DELETE | /cartas/{id}                    | Excluir carta existente                        | 204, 404, 500        |
| POST   | /decks/{id}/adicionar-carta     | Adicionar carta a um deck                      | 200, 400, 404, 500   |
| DELETE | /decks/{id}/remover-carta/{cid}| Remover carta de um deck                      | 204, 404, 500        |
| GET    | /formatos                       | Listar formatos válidos de decks               | 200, 500             |
| POST   | /importar-deck                  | Importar deck por texto ou arquivo             | 201, 400, 500        |
| GET    | /decks/{id}/exportar            | Exportar deck como texto                       | 200, 404, 500        |
| GET    | /decks/usuario/{usuarioId}      | Listar decks de um usuário específico          | 200, 404, 500        |
| POST   | /usuarios                       | Criar novo usuário                             | 201, 400, 500        |
| GET    | /usuarios/{id}                  | Buscar dados do usuário                        | 200, 404, 500        |
| POST   | /login                          | Autenticar usuário                             | 200, 401, 500        |
| GET    | /decks/{id}/estatisticas        | Ver estatísticas do deck (tipos, cores, etc.)  | 200, 404, 500        |

## 3. DTOs e Modelos de Dados

### DeckDTO

```json
{
  "id": 1,
  "nome": "Mono Red Aggro",
  "formato": "Standard",
  "descricao": "Deck focado em dano rápido e direto.",
  "cartas": [
    {
      "id": 101,
      "nome": "Shock",
      "tipo": "Instantâneo",
      "cor": "Vermelho",
      "custoMana": "R",
      "quantidade": 4
    }
  ],
  "dataCriacao": "2025-04-20T15:30:00Z"
}
```
### CartaDTO
```json
{
  "id": 101,
  "nome": "Shock",
  "tipo": "Instantâneo",
  "cor": "Vermelho",
  "custoMana": "R",
  "descricao": "Causa 2 de dano a qualquer alvo."
}
```
### UsuarioDTO
```json
{
  "id": 501,
  "nome": "João Silva",
  "email": "joao@example.com"
}
```
### LoginDTO
```json
{
  "email": "joao@example.com",
  "senha": "********"
}
```

