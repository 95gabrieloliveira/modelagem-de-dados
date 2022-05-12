## CRUD SQL

## Resume da sigla
- C -> CREATE (INSERT,inserir dados)
- R -> READ (SELECT, Leitura de dados)
- U -> UPDATE (Update, atualizar dados)
- D -> DELETE (DELETE, excluir dados)

## FABRICANTES

INSERT INTO fabricantes (nome) VALUE('Dell');
INSERT INTO fabricantes (nome) VALUE('Apple');
INSERT INTO fabricantes (nome) VALUE('Asus');

INSERT INTO fabricantes (nome) value ('Samsung'), ('Microsoft'),('Brastemp');

### PRODUTOS
INSERT INTO produtos (nome, preco, quantidade, descricao, fabricante_id) VALUES('TV LED', 2000, 5, 'TV de última geração', 5);

INSERT INTO produtos (nome, preco, quantidade, descricao, fabricante_id) VALUES('IPHONE XYZ', 5500.79, 8, 'Smartphone caro para caramba', 3);

## INSERT
INSERT INTO produtos(nome, preco, quantidade, descricao, fabricante_id) VALUES
(
    'Geladeira',
    1500,
    10,
    'Refrigerador Frost-free com acesso à Internet das Coisas e bla bla bla',
    7 
),
(
    'iPad Mini',
    5000,
    8,
    'Tablet Apple com tela retina display de 4k, memória interna de 64GB, acesso ao iCloud.', 3
),
(
    'Xbox',
    2500,
    6,
    'Console de última geração com acesso aos melhores jogos e bla bla', 6
),
(
    'Ultrabook',
    4500.68,
    12,
    'Equipamento com processador AMD Ryzen5, 12GB de RAM, placa de vídeo RTX',  1
),
(
    'Headset',
    120,
    9,
    'Fone de ouvido USB com alta qualidade',
    6
),
(
    'Tablet Android',
    4999,
    3,
    'Tablet com a versão 12 do sistema operacional da Google, possui tela de 10 polegadas e armazenamento de 64GB.',
    5
);

## SELECT
SELECT nome, preco FROM produtos;
SELECT preco, nome FROM produtos;
<!-- Selecionar produtos X -->

SELECT nome, preco FROM produtos WHERE preco <3000;
<!-- Selecionar produtos com o preço abaixo de 3 mil -->

SELECT nome, preco FROM produtos WHERE preco <3000 AND preco >2000;
<!-- Selecionar produtos com o preço abaixo de 3000 e acima de 2000 -->

SELECT nome, preco FROM produtos WHERE fabricante_id = 3 OR fabricante_id = 1;
 <!-- Selecionar produtos das fabricantes Apple e Asus -->
 <!-- = Comparar -->

SELECT nome, descricao FROM produtos
ORDER BY nome;
<!-- Mostrar em ordem alfabetica Padrão -->

SELECT nome, descricao FROM produtos
ORDER BY nome DESC;
<!-- Mostrar em ordem alfabetica Decrescente -->

SELECT produtos.nome AS Produto,
fabricantes.nome AS Fabricante, 
produtos.preco As Preço, 
produtos.quantidade AS Quantidade
FROM produtos INNER JOIN fabricantes ON produtos.fabricante_id = fabricantes.id
<!-- --Juntar tabelas -->

-- INNER JOIN: comando que permite juntar duas ou mais tabelas
-- ON: comando para indicar a maneira como as tabelas são juntadas
-- AS: comando que permite dar um apelido para as colunas

## UPDATE

UPDATE fabricantes SET nome = 'LG DO BRASIL' Where id = 4; -- SEMPRE USE WHERE, SEMPRE DÊ UMA CONDIÇÂO

## DELETE
delete FROM produtos 
WHERE id = 5; -- SEMPRE USE WHERE, SEMPRE DÊ UMA CONDIÇÂO