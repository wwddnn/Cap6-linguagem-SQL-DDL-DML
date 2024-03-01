# inserir dados nas tabelas criadas.

# inserir dados da tb_categoria
```
INSERT INTO tb_categoria(descricao, preco_diario) VALUES('Básico', 60.0);
INSERT INTO tb_categoria(descricao, preco_diario) VALUES('Luxo', 150.0);
```

# inserir dados da tb_sede
```
INSERT INTO tb_sede(localidade_s, localidade_w) VALUES(18.28272, 23.38474);
```

# inserir dados da tb_carro
```
INSERT INTO tb_carro(modelo, placa, cor, ano, data_aquisicao, categoria_id, sede_id) VALUES('Polo', 'HDD9383', 0, 2015, '2015-07-21', 1, 1);
INSERT INTO tb_carro(modelo, placa, cor, ano, data_aquisicao, categoria_id, sede_id) VALUES('Fusion', 'PEH3837', 1, 2016, '2016-12-25', 2, 1);
```

obs antes da tb_carro, temos que fazer a tb_sede e também tb_categoria. justamente porque a tb_carro depende dessas.

# inserir dados da tb_estado
```
INSERT INTO tb_estado(nome) VALUES('São Paulo');
```

# inserir dados da tb_cidade
```
INSERT INTO tb_cidade(nome, estado_id) VALUES('São Paulo', 1);
```

# inserir dados da tb_endereco
```
INSERT INTO tb_endereco(logradouro, numero, complemento, bairro, cep, cidade_id) VALUES('Rua Flores', 205, 'Bloco C', 'Jardim', 38400282, 1);
```

# inserir dados na tb_cliente
```
INSERT INTO tb_cliente(cpf, nome, email) VALUES('9838673610', 'Maria Silva', 'maria@gmail.com');
INSERT INTO tb_cliente(cpf, nome, email) VALUES('58236392715', 'Joaquim Jorge', 'joaquim@gmail.com');`
```

obs. como eu inseri errado o cpf da maria clara. agora tenho que fazer um UPDATE conforme abaixo, para consertar esse cpf que lancei errado.

```
UPDATE tb_cliente SET cpf = '93838673610' WHERE cpf = '9838673610';
```

# inserir dados na tb_telefone

```
INSERT INTO tb_telefone(cpf, numero) VALUES('93838673610', '37635393');
INSERT INTO tb_telefone(cpf, numero) VALUES('58236392715', '37636364');
INSERT INTO tb_telefone(cpf, numero) VALUES('58236392715', '89988464');
```

# inserir dados tb_locacao
```
INSERT INTO tb_locacao(instante_locacao, instante_devolucao, cliente_id, carro_id, local_de_retirada_id) VALUES(TIMESTAMP WITH TIME ZONE '2017-09-30T13:34:00Z', TIMESTAMP WITH TIME ZONE '2017-10-04T14:10:00', '93838673610', 1, 1);
INSERT INTO tb_locacao(instante_locacao, instante_devolucao, cliente_id, carro_id, local_de_retirada_id) VALUES(TIMESTAMP WITH TIME ZONE '2017-11-11T12:00:00Z', TIMESTAMP WITH TIME ZONE '2017-11-15T13:00:00', '93838673610', 2, 1);
INSERT INTO tb_locacao(instante_locacao, instante_devolucao, cliente_id, carro_id, local_de_retirada_id) VALUES(TIMESTAMP WITH TIME ZONE '2017-09-30T13:34:00Z', TIMESTAMP WITH TIME ZONE '2018-07-31T03:10:00', '58236392715', 2, 1);
```

obs. para seguir norma padrão iso e para reconhecer o timestamp em vários banco de dados, usamos o TIMESTAMP WITH TIME ZONE.

# inserir dados tb_locacao_diaria
```
INSERT INTO tb_locacao_diaria(id, dias_previstos) VALUES(1, 4);
INSERT INTO tb_locacao_diaria(id, dias_previstos) VALUES(2, 4);
```
obs o id é inserido manualmente na hora do uso pela pessoa, por isso tem aqui o tipo int, ao inves de serial.

# inserir dados tb_locacao_longo_periodo
```
INSERT INTO tb_locacao_longo_periodo(id, porcentagem_desconto) VALUES(3, 50.0);
```
obs o id é inserido manualmente na hora do uso pela pessoa, por isso tem aqui o tipo int, ao inves de serial.
