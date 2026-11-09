# Baozi Store - API REST

API REST simples para controle de clientes, produtos e pedidos de uma loja de pao chines realizada como parte da matéria de Desenvolvimento Web - Back End na UNINTER ADS 2026.

**Tecnologias:** Java 17, Spring Boot 3, Spring Data JPA, H2, Postman.

## Como executar
1. Abra o projeto no em sua IDE de escolha pessoal ex: IntelliJ / Eclipse / VS Code (projeto Maven).
2. Execute a classe `BaoziStoreApplication` (ou `mvn spring-boot:run`).
3. A API sobe em `http://localhost:8080`.

Banco padrao: H2 em arquivo (`./data/baozidb`). Console: `http://localhost:8080/h2-console`
(JDBC URL `jdbc:h2:file:./data/baozidb`, usuario `sa`, senha vazia).

## Estrutura
- `model` - entidades JPA (Cliente, Produto, Pedido)
- `repository` - interfaces Spring Data JPA
- `controller` - endpoints REST

## Endpoints (para /clientes, /produtos e /pedidos)
| Metodo | URL | Descricao |
|---|---|---|
| POST | /{recurso} | Criar |
| GET | /{recurso} | Listar todos |
| GET | /{recurso}/{id} | Consultar por ID |
| DELETE | /{recurso}/{id} | Apagar |

## Exemplos de JSON
POST /clientes
```json
{ "nome": "MauricioMiller5420907", "clienteDesde": "2026-11-09" }
```
POST /produtos
```json
{ "nome": "Baozi de Carne", "preco": 8.50, "estoque": true }
```
POST /pedidos
```json
{ "cliente": { "id": 1 }, "produto": { "id": 1 }, "quantidade": 10 }
```
