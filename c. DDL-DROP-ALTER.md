
# SQL: DDL - DROP
Esse comando apaga a estrutura de um banco de dados, tabela, visão, etc.

```
DROP { DATABASE | TABLE };
```

# REMOVER UMA TABELA OU DATABASE:
Remove uma tabela: obs. vai deletar a tabela tb_funcionario.

```
DROP TABLE tb_funcionario;
```

# Remove uma database: vai deletar o banco de dados empresa.

```
DROP DATABASE empresa;
```

# SQL: DDL - ALTER.
# ALTER:
Altera a estrutura da tabela. criar um novo campo, remover um campo, definir um campo com chave primária, etc.

# ADICIONA E REMOVE UMA NOVA COLUNA PARA A TABELA: 
Adiciona uma coluna na tabela.

```
ALTER TABLE table_name ADD column_name datatype;
```

outro exemplo: cria o campo data_nasc do tipo date.

```
ALTER TABLE tb_funcionario ADD data_nasc DATE;
```

outro exemplo: cria o campo contact_email do tipo varchar e not null.

```
ALTER TABLE tb_funcionario ADD contact_email VARCHAR(10) NOT NULL;
```

outro exemplo: vai remover a coluna data_nasc da tabela.

```
ALTER TABLE tb_funcionario DROP COLUMN data_nasc;
```

# RENOMEIA O CAMPO DE UMA TABELA: 
Altera o nome da coluna, era contact_email vou mudar para email. obs. o que esta em colchetes é opcional.

```
ATER TABLE tb_funcionario RENAME [COLUMN] contact_email TO email;
```

# ALTERA O TIPO DE DADO DE UM CAMPO: 
Altera o tipo de dado da coluna. quero mudar para varchar (20).

```
ALTER TABLE tb_funcionario ALTER [COLUMN] email TYPE VARCHAR(20);
```

# ADICIONA E REMOVE UMA PRIMARY KEY NO CAMPO: 
Adiciona uma chave primária no campo id. 

```
ALTER TABLE tb_funcionario ADD PRIMARY KEY(id);
```

outro exemplo: remove uma chave primária. esse nome da constraint consigo ao clicar com terceiro botão do mouse em tb_funcionario e depois em properties e depois em constraint para ver o nome da restrição dessa primary key.

```
ALTER TABLE tb_funcionario DROP CONSTRAINT table_example_pkey;
```


```
ALTER TABLE tb_funcionario ADD FOREIGN KEY(cod_cargo) REFERENCES tb_cargo(id);
```

outro exemplo: remove uma chave estrangeira (FK). nome da constraint consigo indo com terceiro botão do mouse em tb_funcionario, depois em properties, depois em constraint e vejo nome da foreing key. 

```
ALTER TABLE tb_funcionario DROP CONSTRAINT tb_funcionario_cod_cargo_fkey;
```