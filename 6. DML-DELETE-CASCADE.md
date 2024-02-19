# DML: DELETE-RESTRICT-CASCADE

Usar o comando DELETE com as propriedades RESTRICT ou CASCADE, que fazem parte da FOREIGN KEY.

A RESTRICT é a padrão, não deixa deletar o registro na tabela tb_cargo por exemplo, porque na tabela tb_funcionario tem uma chave estrangeira referenciando a tb_cargo. 
Funciona como uma proteção ao código! Isso vale tanto para os campos da tabela tb_cargo quanto para a tabela tb_departamento. 

Já com o CASCADE é possível deletar sim o registro na tabela tb_cargo por exemplo. Usar com cuidado !

```
DELETE FROM table_name WHERE predicate;
```

# Podemos usar o SELECT para fazer uma consulta a tabela tb_cargo
obs. para consultar todos os registros de uma tabela, apenas para consultar, usar o comando abaixo: nesse exemplo temos todos os registros da tabela tb_cargo:

```
SELECT * FROM tb_cargo;
```

# Usando o RESTRICT e CASCADE na tabela:
Um exemplo de uso dentro da tabela tb_funcionario:

```
CREATE TABLE tb_funcionario (
	id INT,
	nome VARCHAR(30) NOT NULL,
	data_adm DATE,
	sexo CHAR(1), 
	cod_cargo INT NOT NULL,
	cod_depto INT NOT NULL,
	PRIMARY KEY(id),
	FOREIGN KEY(cod_cargo) REFERENCES tb_cargo(id) ON DELETE RESTRICT,
	FOREIGN KEY(cod_depto) REFERENCES tb_departamento(id)
);
```

obs. onde esta ON DELETE RESTRICT, poderia usar no lugar desse, o ON DELETE CASCADE.

# Podemos usar SELECT com ORDER BY e com a ordem decrescente DESC. Para esse exemplo a ordem será decrescente de 5 ate 1 para o cod_cargo

```
SELECT * FROM tb_funcionario ORDER BY cod_cargo DESC;
```

# Podemos também usar o SELECT com ORDER BY e DESC para tabela tb_cargo, no campo salario. Esse será exibido de forma decrescente

```
SELECT * FROM tb_cargo ORDER BY salario DESC;
```
# Para deletar o cargo 5 da tabela tb_cargo, mas tem que estar como CASCADE:

```
DELETE FROM tb_cargo WHERE id = 5;
```

obs. como essa tabela tem relação com a tabela tb_funcionario, então quando eu deleto o cargo 5 da tabela tb_cargo, significa que vou automaticamente em forma de CASCADE deletar os funcionários que tem esse cargo 5 na tabela tb_funcionario.







