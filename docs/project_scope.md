# Escopo do Projeto
O objetivo deste projeto é desenvolver um sistema de gestão de inventário para uma loja de artesanato online. O sistema visa gerenciar informações cruciais sobre produtos, fornecedores, pedidos e clientes. As principais entidades consideradas são "Produto", "Fornecedor", "Pedido" e "Cliente". O foco inicial será a implementação das operações CRUD (Criar, Ler, Atualizar e Excluir) para a entidade "Cliente" utilizando a biblioteca mysql.connector para a conexão com o banco de dados MySQL.

## Estrutura de Entidades
### Produto
**Atributos Essenciais:**
- ID do Produto
- Nome
- Descrição
- Preço
- Quantidade em Estoque
### Fornecedor
**Atributos Essenciais:**
- ID do Fornecedor
- Nome
- Telefone
### Pedido
**Atributos Essenciais:**
- ID do Pedido
- Data do Pedido
- Status do Pedido
- Produtos no Pedido
- Cliente Associado
### Cliente
**Atributos Essenciais:**
- ID do Cliente
- Nome
- Endereço
- Telefone

# Conexão com Banco de Dados (MySQL) utilizando mysql.connector
Para realizar a conexão com o banco de dados MySQL em Python, o projeto utilizará a biblioteca mysql.connector. Abaixo está um exemplo básico de como estabelecer uma conexão:
  ```bash
  import mysql.connector

  # Configuração da Conexão
  db_config = {
      "host": "seu_host",
      "user": "seu_usuario",
      "password": "sua_senha",
      "database": "seu_banco_de_dados"
  }
  
  # Estabelece a Conexão
  connection = mysql.connector.connect(**db_config)
  
  # Cria um Cursor
  cursor = connection.cursor()
  
  # Operações no Banco de Dados...
  
  # Fecha o Cursor e a Conexão
  cursor.close()
  connection.close()
  ```

Lembre-se de substituir "seu_host", "seu_usuario", "sua_senha" e "seu_banco_de_dados" pelos valores específicos do seu ambiente.

# Operações CRUD do Cliente
Ao executar o arquivo main as opções serão fornecidas.
