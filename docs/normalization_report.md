# Relatório
Este relatório descreve a normalização aplicada ao esquema inicial do banco de dados para o projeto da loja de
artesanato online. A normalização é um processo vital no design de banco de dados, que visa eliminar redundâncias
e dependências indesejadas, melhorando a eficiência, integridade e manutenibilidade do sistema.

### 3ª Forma Normal (3FN)
A Terceira Forma Normal (3FN) é um dos estágios da normalização que se concentra na remoção de dependências
transitivas. Uma tabela está na 3FN quando estiver na 2ª Forma Normal e não houver dependências transitivas
de atributos não chave.

### Implementação da 3FN
No esquema original, notei algumas potenciais violações da 3FN que podem ser corrigidas:

- Tabela Clientes:
O atributo nome pode ser divido de forma atômica para p_nome e sobrenome.
Os atributos id_endereco e id_telefone dependem diretamente do cliente, portanto, não há dependências transitivas.

- Tabela Fornecedor:
Os atributos id_endereco e id_telefone dependem diretamente do fornecedor, sem dependências transitivas.

- Tabela Enderecos:
Os atributos logradouro, numero, cep dependem diretamente do endereço, sem dependências transitivas.

- Tabela Cidade:
Os atributos nome e uf_id dependem diretamente da cidade, sem dependências transitivas.

### Tabelas normalizadas
![image](https://github.com/guizen-dev/python-mysql-commercedb/assets/94479811/61f108e8-8f78-4a8b-8621-939a8154a8ae)
