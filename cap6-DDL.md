## DDL:
DDL vai permitir alteramos as tabelas do banco de dados. envolve os metadados de um banco de dados.


- Comando CREATE: obs fazer em cada linha uma coluna, na última linha defino as constrains que são as chaves primárias da minha tabela.
CREATE TABLE table_name (
	column1 datatype column_constraint,
	column2 datatype column_constraint,	
	table_constrains
);


obs buscar no google por ''CREATE table statement postgress'' para ver a estrutura completa do comando. serve para sempre que eu quiser saber mais de um comando. nesse caso consigo ver a estrutura do meu comando CREATE. obs tudo que esta nos colchetes são comandos adicionais. consultar nos sites.


- obs datatype: os mais usuais são: 
- CHAR(n) tem tamanho fixo. até 255 caracteres. armazena 4 bytes. 
- VARCHAR(n) tem tamanho variável. até 65535 caracteres. ocupa somente o tamanho do campo.
- TEXT é variável. até 65535 bytes. usado pra guardar texto ou uma descrição.


- obs datatype: numéricos:
- SMALLINTO tamanho 2 bytes. -32768 a 32767. ''UNSIGNED'' não vai permitir valores negativos.
- INTEGER é muito usual, guarda 4 bytes. -2147483648. ''UNSIGNED'' não vai permitir valores negativos.
- SERIAL é similiar ao INTEGER. 4 bytes. gera uma sequência de inteiros que são usados como ''chave primária'' de uma tabela.
- FLOAT 8 bytes. números com ponto flutuante. ex armazenar o salário de uma pessoa.


- obs datatype: data e hora:
- DATE 4 bytes. formato YYYY-MM-DD
- TIME 8 bytes. formato HH:MI:SS
- TIMESTAMP é a junção do date com o time. tem 8 bytes. formato YYYY-MM--DD HH:MI:SS


- Restrições de integridade:
- Restrição NOT NULL : colunas de preenchimento obrigatório. proibido valor nulo. tem que ser preenchido.
- Restrição DEFAULT : associa um valor default para um atributo caso nenhum outro valor seja especificado.

exemplo
CREATE TABLE cliente (
	nome varchar(20) NOT NULL,
	saldo int DEFAULT 0
);
obs. comentário sobre o código acima, a coluna nome não pode ser nula, e a coluna saldo tem valor 'padrão' zero caso eu não digite nenhum valor.


- Restrição CHECK : é um predicado que precisa ser satisfeito por todas as tuplas de uma relação.
exemplo
CREATE TABLE cliente (
	saldo int CHECK(saldo >= 0)
);
obs. comentário sobre o código acima, o saldo vai ter que ser maior ou igual a zero. se tentar incluir um cliente com saldo negativo ele vai barrar a inserção desse cliente.


- Restrição de integridade - Chave:
- PRIMARY KEY conjunto de atributos que formam a chave primária. os atributos são implicitamente NOT NULL,porque não podemos ter um campo chave primária nulo. 
Há duas formas de definir chave primária:
exemplo1
CREATE TABLE cliente (
	id serial PRIMARY KEY
);
obs. comentário sobre o código acima, vou ter um campo id que é do tipo serial ou seja é auto incrementável. esse campo id é um campo PRIMARY KEY.

exemplo2
CREATE TABLE cliente (
	id serial,
	PRIMARY KEY (id)
);
obs. comentário sobre o código acima, uma linha é para o campo e seus atributos, e a linha a seguir é para a restrição PRIMARY KEY e entre parênteses coloco o campo nesse caso é meu id que é chave primária.
obs. essa forma é mais interessante de usar quando eu tiver mais de um campo como chave primária. nesse caso eu só tive o campo id.


- Restrição de integridade - Chave:
- Cláusula UNIQUE não permite valores duplicados para um atributo.
exemplo
CREATE TABLE cliente (
	id int PRIMARY KEY,
	rg VARCHAR(12) UNIQUE
);
obs, comentário do código acima, o campo rg não pode ser repetido ou seja eu não posso ter valor repetido de rg na coluna, mas repara que não coloquei o rg como primary key.


- Restrição de integridade - Chave:
- Cláusula FOREIGN KEY usada para definir uma chave estrangeira.
exemplo1
CREATE TABLE cliente (
	id int PRIMARY KEY,
	nome VARCHAR(20) NOT NULL
);


exemplo2
CREATE TABLE fone_cliente (
	id int, 
	fone varchar(12)
	PRIMARY KEY(id, fone),
	FOREIGN KEY(id) references cliente(id)
);
obs. comentário do código acima, na tabela cliente meu id e nome são chave primária. já na tabela fone_cliente meu id e fone são chave primárias, e vou citar esse id como a chave estrangeira, tem que usar a palavra reservada 'references'. nesse caso o id é uma chave primária e também uma chave estrangeira. 


















