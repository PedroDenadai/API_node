# Projeto de Gerenciamento de Produtos

Este é um projeto simples de gerenciamento de produtos usando Node.js e Express. Ele inclui um servidor e um banco de dados fictício em memória.

## Estrutura do Projeto

### Banco de Dados (`bancoDeDados.js`)

- `sequencia`: Objeto utilizado para gerar IDs sequenciais.
  - `_id`: Contador de IDs.
  - `id`: Método para obter o próximo ID.
- `produtos`: Objeto que armazena os produtos cadastrados.

#### Funções

- `salvarProduto(produto)`: Salva um produto no banco de dados.
- `getProduto(id)`: Retorna os detalhes de um produto com base no ID.
- `getProdutos()`: Retorna a lista de todos os produtos.
- `excluirProduto(id)`: Exclui um produto do banco de dados.

### Servidor (`servidor.js`)

- `porta`: Porta que o servidor escuta, usei a porta 3003.

#### Pacotes Necessários

- `express`: Framework web para Node.js.
- `body-parser`: Middleware para processar corpos de requisição em JSON e URL-encoded (usei pois começou a dar erro usando somente o express).

#### Endpoints da API

1. **Listar Todos os Produtos**
   - Endpoint: `GET /produtos`
   - Descrição: Retorna a lista de todos os produtos cadastrados.
   - Exemplo de Uso: `GET http://localhost:3003/produtos`

2. **Iniciar o Servidor**
   - Endpoint: `GET /`
   - Descrição: Inicia o servidor e imprime uma mensagem indicando a porta em que está escutando.

3. **Listar Detalhes de um Produto**
   - Endpoint: `GET /produtos/:id`
   - Descrição: Retorna os detalhes de um produto com base no ID fornecido na URL.
   - Exemplo de Uso: `GET http://localhost:3003/produtos/31`

4. **Cadastrar um Novo Produto**
   - Endpoint: `POST /produtos`
   - Descrição: Cadastra um novo produto no banco de dados. Deve receber um corpo JSON contendo `nome` e `preco` do produto.

5. **Atualizar um Produto Existente**
   - Endpoint: `PUT /produtos/:id`
   - Descrição: Atualiza as informações de um produto existente com base no ID fornecido na URL. Deve receber um corpo JSON contendo `nome` e `preco` atualizados.

6. **Excluir um Produto**
   - Endpoint: `DELETE /produtos/:id`
   - Descrição: Exclui um produto do banco de dados com base no ID fornecido na URL.
