# Teste
#Exemplos de queries SQL:
Recuperação simples com SELECT Statement:
SELECT * FROM Cliente;

#Filtros com WHERE Statement:
SELECT nome FROM Produto WHERE estoque > 50;

#Expressões para gerar atributos derivados:
SELECT nome, estoque, (estoque * valor_unitario) AS valor_total FROM Produto;

#Ordenação dos dados com ORDER BY:
SELECT nome, estoque FROM Produto ORDER BY estoque DESC;

#Condições de filtros aos grupos – HAVING Statement:
SELECT cliente_id, COUNT(pedido_id) AS total_pedidos
FROM Pedido
GROUP BY cliente_id
HAVING COUNT(pedido_id) >= 3;

#Junções entre tabelas para fornecer uma perspectiva mais complexa dos dados:
SELECT p.nome AS produto, f.nome AS fornecedor, i.quantidade, i.valor_unitario
FROM Produto p
JOIN Fornecedor f ON p.fornecedor_id = f.fornecedor_id
JOIN ItemPedido i ON p.produto_id = i.produto_id;

Relação de nomes dos fornecedores e nomes dos produtos:
SELECT f.nome AS fornecedor, GROUP_CONCAT(p.nome SEPARATOR ', ') AS produtos
FROM Fornecedor f
JOIN Produto p ON f.fornecedor_id = p.fornecedor_id
GROUP BY f.nome;

Lembre-se de que essas consultas são apenas exemplos e você pode personalizá-las de acordo com as suas necessidades.
