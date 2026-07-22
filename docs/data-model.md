# Modelagem de Dados

## Entidades

### Pedido (orders)

| Coluna     | Tipo      | Descrição                                    |
|------------|-----------|----------------------------------------------|
| id         | INTEGER   | Identificador único, gerado automaticamente  |
| customer   | TEXT      | Nome do cliente                              |
| status     | TEXT      | Estado do pedido (ex.: pending, completed)   |
| created_at | TIMESTAMP | Data e hora de criação, automática           |

### Item (items)

| Coluna      | Tipo    | Descrição                            |
|-------------|---------|--------------------------------------|
| id          | INTEGER | Identificador único, gerado auto.    |
| order_id    | INTEGER | Chave estrangeira → orders(id)       |
| sku         | TEXT    | Código do item                       |
| description | TEXT    | Descrição do item                    |
| quantity    | INTEGER | Quantidade                           |

## Relacionamento

- Um pedido pode ter múltiplos itens, mas cada item pertence a apenas um pedido. Isso é representado pela chave estrangeira `order_id` na tabela `items`, que referencia a coluna `id` da tabela `orders`.

- A relação entre as tabelas é do tipo "um para muitos" (1:N), onde um pedido pode conter vários itens, mas cada item está associado a apenas um pedido específico.