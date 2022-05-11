# Comandos SQL para modelagem física

## Criar banco de dados
CREATE DATABASE vendas_gabriel CHARACTER SET utf8mb4;

## Entrar no banco de dados criado
USE DATABASE vendas_gabriel;

## Criar tabela Fabricantes
CREATE TABLE fabricantes (
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(45) NOT NULL
);

## Criar tabela Produtos
CREATE TABLE produtor (
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(45) NOT NULL,
    preco DECIMAL(8,2) NOT NULL,
    quantidade SMALLINT NULL,
    descricao TEXT(1000) NULL,
    fabricante_id INT
);

## Alterando a tabela para criar um relacionamento por meio da chave estrangeira
ALTER TABLE produtos
    ADD CONSTRAINT fk_produtos_fabricantes
    FOREIGN KEY(fabricante_id) REFERENCES fabricantes(id);

