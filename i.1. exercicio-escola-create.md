# exercicio escola

# criar as tabelas

```
CREATE TABLE tb_curso(
	id SERIAL PRIMARY KEY,
	nome VARCHAR(20) NOT NULL,
	carga_horaria INT,
	valor FLOAT,
	nota_prevista FLOAT NOT NULL,
	nota_minima FLOAT
);

CREATE TABLE tb_turma(
	id SERIAL PRIMARY KEY,
	numero INT,
	inicio DATE,
	vagas INT,
	curso_id INT NOT NULL,
	FOREIGN KEY(curso_id) REFERENCES tb_curso(id)
);

CREATE TABLE tb_aluno(
	cpf VARCHAR(12) PRIMARY KEY,
	nome VARCHAR(40) NOT NULL,
	nascimento DATE
);

CREATE TABLE tb_matricula(
	turma_id INT,
	aluno_id VARCHAR(12),
	data DATE,
	prestacoes INT,
	PRIMARY KEY(turma_id, aluno_id),
	FOREIGN KEY(turma_id) REFERENCES tb_turma(id),
	FOREIGN KEY(aluno_id) REFERENCES tb_aluno(cpf)
);

CREATE TABLE tb_avaliacao(
	id SERIAL PRIMARY KEY,
	nota FLOAT NOT NULL,
	data DATE NOT NULL,
	turma_id INT NOT NULL,
	FOREIGN KEY(turma_id) REFERENCES tb_turma(id)
);

CREATE TABLE tb_resultado(
	aluno_id VARCHAR(12),
	avaliacao_id INT,
	nota_obtida FLOAT,
	PRIMARY KEY(aluno_id, avaliacao_id),
	FOREIGN KEY(aluno_id) REFERENCES tb_aluno(cpf),
	FOREIGN KEY(avaliacao_id) REFERENCES tb_avaliacao(id)
);
```

obs. para a tabela tb_turma, temos o campo 'inicio' com o tipo DATE ja que precisamos somente da data mesmo, pois se fosse data e hora ele seria do tipo TIMESTAMP.

obs. para tabela tb_matricula, o campo 'aluno_id' tem o tipo VARCHAR(12) pelo motivo de estar ligado ao campo cpf da tabela tb_aluno que é a chave primaria la.

obs. quando usamos PRIMARY KEY em qualquer criação de campo para a tabela, não precisamos usar simultaneamente o NOT NULL. isso porque o PRIMARY KEY ja indica que tem um valor.


