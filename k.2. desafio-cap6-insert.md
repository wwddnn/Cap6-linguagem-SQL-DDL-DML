# desafio cap 6 script de criacao de tabelas e seed.

# inserir os dados nas tabelas

```
INSERT INTO tb_regiao(nome, localidade_s, localidade_w, descricao) VALUES('Vale Central', 33.8088, 70.7644, 'Chile');
INSERT INTO tb_regiao(nome, localidade_s, localidade_w, descricao) VALUES('Serra Gaúcha', 29.3746, 50.8764, 'Sul do Brasil');

INSERT INTO tb_vinicula(nome, descricao, fone, email, regiao_id) VALUES('Santa Rita', 'localizada no vale del maipo e tem mais de 100 anos de história', null, 'santa@gmail.com', 1);
INSERT INTO tb_vinicula(nome, descricao, fone, email, regiao_id) VALUES('Santa Carolina', null, '3395-4422', 'carolina@gmail.com', 1);
INSERT INTO tb_vinicula(nome, descricao, fone, email, regiao_id) VALUES('Garibaldi', 'Vinícula situada na Serra Gaúcha', '9822-3344', 'garibaldi@gmail.com', 2);

INSERT INTO tb_tipo_vinho(nome) VALUES('Tinto');
INSERT INTO tb_tipo_vinho(nome) VALUES('Branco');
INSERT INTO tb_tipo_vinho(nome) VALUES('Rose');
INSERT INTO tb_tipo_vinho(nome) VALUES('Bordeux');

INSERT INTO tb_vinho(nome, tipo_id, preco, vinicula_id) VALUES('Amanda', 1, 100.0, 1);
INSERT INTO tb_vinho(nome, tipo_id, preco, vinicula_id) VALUES('Belinha', 2, 200.0, 1);
INSERT INTO tb_vinho(nome, tipo_id, preco, vinicula_id) VALUES('Camila', 4, 65.0, 2);
INSERT INTO tb_vinho(nome, tipo_id, preco, vinicula_id) VALUES('Daniela', 3, 89.0, 2);
INSERT INTO tb_vinho(nome, tipo_id, preco, vinicula_id) VALUES('Eduarda', 1, 55.0, 3);
INSERT INTO tb_vinho(nome, tipo_id, preco, vinicula_id) VALUES('Fernanda', 2, 70.0, 3);
```
obs. para o campo localidade vamos escrever o float, sem aspas, na tabela tb_regiao.

obs. para o campo email usamos aspas, pois é um campo varchar(20), na tabela tb_vinicula.

obs. para o campo fone usamos aspas pois é um campo varchar(12) na tabela tb_vinicula.

