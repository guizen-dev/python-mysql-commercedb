create database Loja;
use Loja;

CREATE TABLE Clientes (
	id INT AUTO_INCREMENT PRIMARY KEY,
    p_nome VARCHAR(255) NOT NULL,
    sobrenome VARCHAR(100) NOT NULL,
    cpf VARCHAR(11) NOT NULL,
    data_nasc DATE NOT NULL,
	id_endereco INT NOT NULL,
    id_telefone INT NOT NULL,
	FOREIGN KEY (id_endereco) REFERENCES Enderecos(id),
    FOREIGN KEY (id_telefone) REFERENCES Telefone(id)
);

CREATE TABLE Fornecedor (
	id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(255) NOT NULL,
    cnpj VARCHAR(14) NOT NULL,
    id_endereco INT NOT NULL,
    id_telefone INT NOT NULL,
	FOREIGN KEY (id_endereco) REFERENCES Enderecos(id),
    FOREIGN KEY (id_telefone) REFERENCES Telefone(id)
);

CREATE TABLE Telefone(
	id INT AUTO_INCREMENT PRIMARY KEY,
    telefone INT NOT NULL,
    tipo VARCHAR(20) NOT NULL
);

CREATE TABLE Enderecos (
	id INT AUTO_INCREMENT PRIMARY KEY,
    logradouro VARCHAR(100) NOT NULL,
    numero INT NOT NULL,
    cep INT NOT NULL,
    cidade_id INT NOT NULL,
    FOREIGN KEY (cidade_id) REFERENCES Cidade(id)
);

CREATE TABLE Cidade (
	id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(255) NOT NULL,
    uf_id int NOT NULL,
    FOREIGN KEY (uf_id) REFERENCES Uf(id)
);

CREATE TABLE Uf (
	id INT AUTO_INCREMENT PRIMARY KEY,
    nome varchar(2) NOT NULL
);

CREATE TABLE Pedido (
    id INT PRIMARY KEY AUTO_INCREMENT,
    cliente_id INT,
    data_pedido DATE NOT NULL,
    FOREIGN KEY (cliente_id) REFERENCES Clientes(id)
);

CREATE TABLE ItemPedido (
    id INT PRIMARY KEY AUTO_INCREMENT,
    pedido_id INT,
    produto_id INT,
    quantidade INT NOT NULL,
    preco_unitario DECIMAL(10, 2) NOT NULL,
    FOREIGN KEY (pedido_id) REFERENCES Pedido(id),
    FOREIGN KEY (produto_id) REFERENCES Produto(id)
);

CREATE TABLE Produto (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(255) NOT NULL,
    descricao TEXT,
    preco DECIMAL(10, 2) NOT NULL,
    quantidadeEstoque INT NOT NULL,
    fornecedor_id INT,
    FOREIGN KEY (fornecedor_id) REFERENCES Fornecedor(id)
);