# desafio cap 6 script de criacao de tabelas e seed.


# criação das tabelas

```
CREATE TABLE tb_regiao(
	id SERIAL PRIMARY KEY,
	nome VARCHAR(20) NOT NULL,
	localidade_s FLOAT NOT NULL,
	localidade_w FLOAT NOT NULL,
	descricao VARCHAR(20)
);

CREATE TABLE tb_vinicula(
	id SERIAL PRIMARY KEY,
	nome VARCHAR(20) NOT NULL,
	descricao TEXT,	
	fone VARCHAR(12),
	email VARCHAR(20) UNIQUE NOT NULL,
	regiao_id INT NOT NULL,
	FOREIGN KEY(regiao_id) REFERENCES tb_regiao(id)
);

CREATE TABLE tb_tipo_vinho (
	id SERIAL PRIMARY KEY,
	nome VARCHAR(20) NOT NULL
);

CREATE TABLE tb_vinho(
	id SERIAL PRIMARY KEY,
	nome VARCHAR(20),
	tipo_id INT NOT NULL,
	preco FLOAT NOT NULL,
	vinicula_id INT NOT NULL,
	FOREIGN KEY(tipo_id) REFERENCES tb_tipo_vinho(id),
	FOREIGN KEY(vinicula_id) REFERENCES tb_vinicula(id)
);
```
obs. para o campo localidade usamos o tipo FLOAT e NOT NULL, na tabela tb_regiao.

obs. para o campo fone usamos o tipo VARCHAR(12) na tabela tb_vinicula.

obs. para o campo descricao usamoso tipo TEXT para dar mais liberdade de texto para escrever, na tabela tb_vinicula.



