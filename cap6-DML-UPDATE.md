# SQL: DML - UPDATE.
- Altera os dados específicos de uma tabela.

UPDATE table_name SET column = new_value WHERE predicate 

- vou atualizar o nome de um funcionário, por exemplo, ele procura no id 4 da tabela funcionario. 
- obs. tem que usar o WHERE como predicado, senão atualiza para todos os funcionários.

UPDATE tb_funcionario SET nome = 'Ricardo Fernandes Oliveira' WHERE id = 4;

- vou atualizar o nivel da funcionaria, dentro da tabela funcionario, por exemplo. 
- obs. tem que usar o WHERE como predicado para ele ir exatamente naquele funcionário.

UPDATE tb_funcionario SET cod_cargo = 3 WHERE id = 3;