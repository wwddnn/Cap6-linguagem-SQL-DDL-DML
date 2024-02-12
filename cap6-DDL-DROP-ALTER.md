## DDL : Comando DROP.

- Esse comando apaga a estrutura de um banco de dados, tabela, visão, etc.

DROP { DATABASE | TABLE };

### Remove uma tabela:
Exemplo
DROP TABLE tb_funcionario;
- obs. comentário do código acima, vai deletar a tabela tb_funcionario.


### Remove uma database:
Exemplo
DROP DATABASE empresa;
- obs. comantário do código acima, vai deletar o banco de dados empresa.



## DDL : Comando ALTER.

- Altera a estrutura da tabela. criar um novo campo, remover um campo, definir um campo com chave primária, etc.


### Adiciona e remove uma nova coluna para a tabela:
Exemplo
ALTER TABLE table_name ADD column_name datatype;
- obs. vai adicionar uma coluna na tabela.

Exemplo2
ALTER TABLE tb_funcionario ADD data_nasc DATE;
- obs. cria o campo data_nasc do tipo date.

Exemplo3
ALTER TABLE tb_funcionario ADD contact_email VARCHAR(10) NOT NULL;
- obs. cria o campo contact_email do tipo varchar e not null.

Exemplo4
ALTER TABLE tb_funcionario DROP COLUMN data_nasc;
- obs. vai remover a coluna data_nasc da tabela.


### Renomeia o campo de uma tabela:
Exemplo
ATER TABLE tb_funcionario RENAME [COLUMN] contact_email TO email;
- obs. altera o nome da coluna, era contact_email vou mudar para email.
- obs. o que esta em colchetes é opcional.

### Altera o tipo de dado de um campo:
Exemplo
ALTER TABLE tb_funcionario ALTER [COLUMN] email TYPE VARCHAR(20);
- obs. altera o tipo de dado da coluna. quero mudar para varchar (20).


### Adiciona e remove uma primary key no campo:
Exemplo
ALTER TABLE tb_funcionario ADD PRIMARY KEY(id);
- obs. adicionar uma chave primária no campo id. 

Exemplo
ALTER TABLE tb_funcionario DROP CONSTRAINT table_example_pkey;
- obs. remover uma chave primária. esse nome da constraint consigo ao clicar com terceiro botão do mouse em tb_funcionario e depois em properties e depois em constraint para ver o nome da restrição dessa primary key.


### Adiciona e remove uma foreign key do campo:
Exemplo
ALTER TABLE tb_funcionario ADD FOREIGN KEY(cod_cargo) REFERENCES tb_cargo(id);
- obs. adicionar uma chave estrangeira (FK).

Exemplo
ALTER TABLE tb_funcionario DROP CONSTRAINT tb_funcionario_cod_cargo_fkey;
- obs. remover uma chave estrangeira (FK). nome da constraint consigo indo com terceiro botão do mouse em tb_funcionario, depois em properties, depois em constraint e vejo nome da foreing key. 

