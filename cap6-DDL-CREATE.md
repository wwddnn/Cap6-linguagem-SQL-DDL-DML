# SQL: DDL
DDL vai permitir alteramos as tabelas do banco de dados. envolve os metadados de um banco de dados.

# DDL: CREATE
Cada linha do código abaixo é uma coluna, na última linha defino as constrains que são as chaves primárias da minha tabela.

`
CREATE TABLE table_name (
	column1 datatype column_constraint,
	column2 datatype column_constraint,	
	table_constrains
);
`

obs buscar no google por ''CREATE table statement postgress'' para ver a estrutura completa do comando. serve para sempre que eu quiser saber mais de um comando. nesse caso consigo ver a estrutura do meu comando CREATE. 

obs tudo que esta nos colchetes são comandos adicionais. consultar nos sites.

# DATATYPES mais usados
CHAR(n) tem tamanho fixo. até 255 caracteres. armazena 4 bytes. 

VARCHAR(n) tem tamanho variável. até 65535 caracteres. ocupa somente o tamanho do campo.

TEXT é variável. até 65535 bytes. usado pra guardar texto ou uma descrição.



# DATATYPE: NUMÉRICOS
SMALLINTO tamanho 2 bytes. -32768 a 32767. ''UNSIGNED'' não vai permitir valores negativos.

INTEGER é muito usual, guarda 4 bytes. -2147483648. ''UNSIGNED'' não vai permitir valores negativos.

SERIAL é similiar ao INTEGER. 4 bytes. gera uma sequência de inteiros que são usados como ''chave primária'' de uma tabela.

FLOAT 8 bytes. números com ponto flutuante. ex armazenar o salário de uma pessoa.


# DATATYPE: DATA E HORA
DATE 4 bytes. formato YYYY-MM-DD

TIME 8 bytes. formato HH:MI:SS

TIMESTAMP é a junção do date com o time. tem 8 bytes. formato YYYY-MM--DD HH:MI:SS


# RESTRIÇÕES DE INTEGRIDADE
Restrição NOT NULL : colunas de preenchimento obrigatório. proibido valor nulo. tem que ser preenchido.

Restrição DEFAULT : associa um valor default para um atributo caso nenhum outro valor seja especificado.

a coluna nome não pode ser nula, e a coluna saldo tem valor 'padrão' zero caso eu não digite nenhum valor.

`
CREATE TABLE cliente (
	nome varchar(20) NOT NULL,
	saldo int DEFAULT 0
);
`

Restrição CHECK : é um predicado que precisa ser satisfeito por todas as tuplas de uma relação.
o saldo vai ter que ser maior ou igual a zero. se tentar incluir um cliente com saldo negativo ele vai barrar a inserção desse cliente.

`
CREATE TABLE cliente (
	saldo int CHECK(saldo >= 0)
);
`

# RESTRIÇÃO DE INTEGRIDADE - PRIMARY KEY
PRIMARY KEY: conjunto de atributos que formam a chave primária. os atributos são implicitamente NOT NULL, porque não podemos ter um campo chave primária nulo. 

Há duas formas de definir chave primária: 

FORMA1:

vou ter um campo id que é do tipo serial ou seja é auto incrementável. esse campo id é um campo PRIMARY KEY.

`
CREATE TABLE cliente (
	id serial PRIMARY KEY
);
`

FORMA2: 

uma linha é para o campo e seus atributos, e a linha a seguir é para a restrição PRIMARY KEY e entre parênteses coloco o campo nesse caso é meu id que é chave primária. obs. essa forma é mais interessante de usar quando eu tiver mais de um campo como chave primária. nesse caso eu só tive o campo id.

`
CREATE TABLE cliente (
	id serial,
	PRIMARY KEY (id)
);
`

# RESTRIÇÃO DE INTEGRIDADE - Chave
Cláusula UNIQUE:  não permite valores duplicados para um atributo.

`
CREATE TABLE cliente (
	id int PRIMARY KEY,
	rg VARCHAR(12) UNIQUE
);
`

obs, comentário do código acima, o campo rg não pode ser repetido ou seja eu não posso ter valor repetido de rg na coluna, mas repara que não coloquei o rg como primary key.

# RESTRIÇÃO DE INTEGRIDADE - FOREIGN KEY
Cláusula FOREIGN KEY:  usada para definir uma chave estrangeira.

exemplo1

`
CREATE TABLE cliente (
	id int PRIMARY KEY,
	nome VARCHAR(20) NOT NULL
);
`

exemplo2

`
CREATE TABLE fone_cliente (
	id int, 
	fone varchar(12)
	PRIMARY KEY(id, fone),
	FOREIGN KEY(id) references cliente(id)
);
`

obs. comentário do código acima, na tabela cliente meu id e nome são chave primária. já na tabela fone_cliente meu id e fone são chave primárias, e vou citar esse id como a chave estrangeira, tem que usar a palavra reservada 'references'. nesse caso o id é uma chave primária e também uma chave estrangeira. 

# PROPRIEDADES DA CHAVE ESTRANGEIRA
RESTRICT: não permite que um registro seja deletado caso alguma tupla esteja referenciando. (esse é o padrão).

CASCADE: deleta o registro de todas as tuplas que referenciam o registro. (usar essa cláusula com cuidado! atenção).

obs. por padrão, o banco de dados usa a cláusula RESTRICT caso nenhuma seja especificada.

exemplo:

`
CREATE TABLE cliente (
	id int PRIMARY KEY, 
	nome varchar(20) NOT NULL
);
`

`
CREATE TABLE fone_cliente (
	id int;
	fone varchar(12);
	PRIMARY KEY(id, fone),
	FOREIGN KEY(id) references cliente(id)
	ON DELETE RESTRICT
);
`

obs. comentário sobre o código acima, a linha On Delete Restrict é para informarmos que esse dado é sensível e não pode deletar. eu coloco abaixo da chave estrangeira para dizer que esse dado que esta se referindo a tupla, não pode ser apagado. na definição da tabela estamos definindo isso de forma explícita. posso usar também o On Delete Cascade, nesse caso vai poder sim deletar as tuplas associadas.


















