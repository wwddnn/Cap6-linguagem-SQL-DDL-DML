# exercicio escola

# inserir dados na tabela tb_curso
```
INSERT INTO tb_curso(nome, carga_horaria, valor, nota_prevista, nota_minima) VALUES('HTML Básico', 10, 80.0, 100.0, 70.0);
```

# inserir dados na tabela tb_turma
```
INSERT INTO tb_turma(numero, inicio, vagas, curso_id) VALUES(1, '2017/09/10', 30, 1);
```

# inserir dados na tabela tb_aluno
```
INSERT INTO tb_aluno(cpf, nome, nascimento) VALUES('736376983-19', 'Carlos Silva', '1990-07-21');
INSERT INTO tb_aluno(cpf, nome, nascimento) VALUES('353847901-22', 'Maria Clara', '1991-09-03');
```

# inserir dados na tabela tb_matricula
```
INSERT INTO tb_matricula(turma_id, aluno_id, data, prestacoes) VALUES(1, '736376983-19', '2017-09-05', 6 );
INSERT INTO tb_matricula(turma_id, aluno_id, data, prestacoes) VALUES(1, '353847901-22', '2017-09-06', 12);
```
# inserir dados na tabela tb_avaliacao
```
INSERT INTO tb_avaliacao(nota, data, turma_id) VALUES(40.0, '2017-10-20', 1);
INSERT INTO tb_avaliacao(nota, data, turma_id) VALUES(60.0, '2017-11-30', 1);
```

# inserir dados na tabela tb_resultado
```
INSERT INTO tb_resultado(aluno_id, avaliacao_id, nota_obtida) VALUES('736376983-19', 1, 35.0);
INSERT INTO tb_resultado(aluno_id, avaliacao_id, nota_obtida) VALUES('353847901-22', 1, 36.5);
INSERT INTO tb_resultado(aluno_id, avaliacao_id, nota_obtida) VALUES('736376983-19', 2, 47.0);
INSERT INTO tb_resultado(aluno_id, avaliacao_id, nota_obtida) VALUES('353847901-22', 2, 52.4);
```
