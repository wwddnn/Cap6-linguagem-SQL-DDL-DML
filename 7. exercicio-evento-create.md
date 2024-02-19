

# Esquema com 4 tabelas:

```
CREATE TABLE tb_categoria(
	id SERIAL PRIMARY KEY,
	descricao VARCHAR(20) NOT NULL
);

CREATE TABLE tb_atividade(
	id SERIAL PRIMARY KEY,
	nome VARCHAR(20) NOT NULL,
	descricao VARCHAR(40),
	preco FLOAT,
	categoria_id INT NOT NULL,
	FOREIGN KEY(categoria_id) REFERENCES tb_categoria(id)
);

CREATE TABLE tb_bloco(
	id SERIAL PRIMARY KEY,
	inicio TIMESTAMP,
	fim TIMESTAMP,
	atividade_id INT NOT NULL,
	FOREIGN KEY(atividade_id) REFERENCES tb_atividade(id)
);

CREATE TABLE tb_participante(
	id SERIAL PRIMARY KEY,
	nome VARCHAR(40) NOT NULL,
	email VARCHAR(20) UNIQUE NOT NULL
);

CREATE TABLE tb_participacao(
	participante_id INT,
	atividade_id INT,
	PRIMARY KEY(participante_id, atividade_id),
	FOREIGN KEY(participante_id) REFERENCES tb_participante(id),
	FOREIGN KEY(atividade_id) REFERENCES tb_atividade(id)
);
```

obs1. na tabela tb_bloco usamos no campo 'inicio', e 'fim', o tipo TIMESTAMP para indicar data e hora.

obs2. na tabela tb_participante usamos no campo 'email' o UNIQUE para dizer que não tem outro email igual na tabela, e também o NOT NULL para não ficar nulo.

obs3. a tabela tb_participacao tem 2 chaves primárias que chamamos de chave composta. dessa forma, escrevemos o PRIMARY KEY no final e entre parênteses os campos que são chave primária na tabela que são 'participante_id' e 'atividade_id'.