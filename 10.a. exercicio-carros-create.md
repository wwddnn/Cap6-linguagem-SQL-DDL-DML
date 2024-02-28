# criando tabelas com CREATE
obs. o ideal é sempre começar a criação pela tabela que não tem chave estrangeira! ! !

# criar a tabela tb_categoria
```
CREATE TABLE tb_categoria(
	id SERIAL PRIMARY KEY,
	descricao VARCHAR(20) NOT NULL,
	preco_diario FLOAT
);
```
# criar a tabela tb_sede e depois a tabela tb_carro
obs. a tabela tb_sede tem que ser criada antes da tabela tb_carro, pois a tabela tb_carro depende dessa tabela tb_sede.

```
CREATE TABLE tb_sede(
	codigo SERIAL PRIMARY KEY,
	localidade_s FLOAT NOT NULL,
	localidade_w FLOAT NOT NULL
);
```
obs. para o campo localidade usamos o tipo FLOAT.

```
CREATE TABLE tb_carro(
	id SERIAL PRIMARY KEY,
	modelo VARCHAR(20) NOT NULL,
	placa VARCHAR(12) NOT NULL,
	cor SMALLINT,
	ano SMALLINT,
	data_aquisicao DATE,
	categoria_id INT NOT NULL,
	sede_id INT NOT NULL,
	FOREIGN KEY(categoria_id) REFERENCES tb_categoria(id),
	FOREIGN KEY(sede_id) REFERENCES tb_sede(codigo)
);
```
obs. para o campo 'cor' e o campo 'ano' usamos o tipo SMALLINT porque não precisa de tantos números.

# criar a tabela tb_estado e depois a tabela tb_cidade e depois a tabela tb_endereco
obs. não podemos criar as tabelas tb_endereco e nem a tabela tb_cidade, sem antes criarmos a tabela tb_estado. porque as duas primeiras tem chave estrangeira em relação a tabela tb_estado.
```
CREATE TABLE tb_estado(
	id SERIAL PRIMARY KEY,
	nome VARCHAR(40) NOT NULL
);
```

```
CREATE TABLE tb_cidade(
	id SERIAL PRIMARY KEY,
	nome VARCHAR(40) NOT NULL,
	estado_id INT NOT NULL,
	FOREIGN KEY(estado_id) REFERENCES tb_estado(id)
)
```

```
CREATE TABLE tb_endereco(
	id SERIAL PRIMARY KEY,
	logradouro VARCHAR(60) NOT NULL,
	numero INT NOT NULL,
	complemento VARCHAR(30), 
	bairro VARCHAR(30) NOT NULL,
	cep VARCHAR(12) NOT NULL,
	cidade_id INT NOT NULL,
	FOREIGN KEY(cidade_id) REFERENCES tb_cidade(id)
);
```

obs. para o campo 'cep' usamos o tipo VARCHAR(12). 

# criar a tabela tb_cliente
```
CREATE TABLE tb_cliente(
	cpf VARCHAR(12) PRIMARY KEY,
	nome VARCHAR(40) NOT NULL,
	email VARCHAR(20) UNIQUE NOT NULL
);
```

obs. o campo 'cpf' em regra usamos sempre o tipo VARCHAR(12), e normmalmente ele fica como um PRIMARY KEY.

obs. o campo 'email' usamos UNIQUE porque não pode ter outro email igual, e também NOT NULL.

# criar a tabela tb_telefone
```
CREATE TABLE tb_telefone(
	cpf VARCHAR(12),
	numero VARCHAR(12),
	PRIMARY KEY(cpf, numero),
	FOREIGN KEY(cpf) REFERENCES tb_cliente(cpf)
);
```
obs. ambos os campos 'cpf' e 'numero' são PRIMARY KEY.

# criar a tabela tb_locacao, e depois das tabelas tb_locacao_diaria e tb_locacao_longo_periodo
```
CREATE TABLE tb_locacao(
	id SERIAL PRIMARY KEY,
	instante_locacao TIMESTAMP NOT NULL,
	instante_devolucao TIMESTAMP NOT NULL,
	cliente_id VARCHAR(12) NOT NULL,
	carro_id INT NOT NULL,
	local_de_retirada_id INT NOT NULL,
	FOREIGN KEY(cliente_id) REFERENCES tb_cliente(cpf),
	FOREIGN KEY(carro_id) REFERENCES tb_carro(id),
	FOREIGN KEY(local_de_retirada_id) REFERENCES tb_sede(codigo)
);
```
obs. atenção para o FOREIGN KEY local_de_retirada_id faz referência a tabela tb_sede no campo 'código'! nãp tem campo id na tabela tb_sede.

```
CREATE TABLE tb_locacao_diaria(
	id INT PRIMARY KEY,
	dias_previstos INT NOT NULL,
	FOREIGN KEY(id) REFERENCES tb_locacao(id)
);
```
obs. o campo id é uma chave primária e ao mesmo tempo uma chave estrangeira.

obs. o campo id usamos o tipo INT para essa tabela tb_locacao_diaria.

```
CREATE TABLE tb_locacao_longo_periodo(
	id INT PRIMARY KEY,
	porcentagem_desconto FLOAT NOT NULL,
	FOREIGN KEY(id) REFERENCES tb_locacao(id)
);
```
