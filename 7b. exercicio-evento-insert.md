# Vamos inserir os registros nas tabelas que foram criadas anteriormente:


# inserir registros na tabela tb_categoria
```
INSERT INTO tb_categoria(descricao) VALUES ('Curso');
INSERT INTO tb_categoria(descricao) VALUES ('Oficina');
```

obs. não precisa inserir o id, porque esse campo foi criado como 'serial' na hora da criação da tabela.


# inserir registros na tabela tb_atividade
```
INSERT INTO tb_atividade(nome, descricao, preco, categoria_id) VALUES('Curso de HTML', 'Aprenda HTML de forma prática', 80.0, 1);
INSERT INTO tb_atividade(nome, descricao, preco, categoria_id) VALUES('Oficina de Github', 'Controle versões de seus projetos', 50.0, 2);
```

obs. idem ao caso acima, onde o id é um 'serial' que foi criado na hora da criação da tabela, então não precisamos inserir o numero do id nesse momento.


# inserir registros na tabela tb_bloco

```
INSERT INTO tb_bloco(inicio, fim, atividade_id) VALUES(TIMESTAMP WITH TIME ZONE '2017-09-25T11:00:00Z', TIMESTAMP WITH TIME ZONE '2017-09-25T14:00:00Z', 1);
INSERT INTO tb_bloco(inicio, fim, atividade_id) VALUES(TIMESTAMP WITH TIME ZONE '2017-09-25T17:00:00Z', TIMESTAMP WITH TIME ZONE '2017-09-25T21:00:00Z', 2);
INSERT INTO tb_bloco(inicio, fim, atividade_id) VALUES(TIMESTAMP WITH TIME ZONE '2017-09-26T11:00:00Z', TIMESTAMP WITH TIME ZONE '2017-09-26T14:00:00Z', 2);
```

obs. ISO 8601 formato padrão para armazenar datas. YYYY-MM-DDThh:mm:ss[.mmm]TZD por isso colocamos o 'T' e também o 'Z', segue exemplo '2017-09-25T11:00:00Z'.

obs. para todos os bancos de dados reconhecerem como UTC usamos o texto TIMESTAMP WITH TIME ZONE antes dessa data e hora UTC.

obs. veja que na primeira linha de código, inserimos o TOMESTAMP WITH TIME ZONE para mostrar que essa data será reconhecida em todo banco de dados. 

obs. também nesse exemplo colocamos as datas em formato UTC que é a hora do meridiano que será exibida na tela, se quisermos que a hora do brasil seja exibida fazer 3hs a menos,
então ficaria '2017-09-25T8:00:00Z' nesse caso vai exibir a hora que temos no brasil.

# inserir registros na tabela 
```
INSERT INTO tb_participante(nome, email) VALUES('José Silva', 'jose@gmail.com');
INSERT INTO tb_participante(nome, email) VALUES('Tiago Faria', 'tiago@gmail.com');
INSERT INTO tb_participante(nome, email) VALUES('Maria do Rosário', 'maria@gmail.com');
INSERT INTO tb_participante(nome, email) VALUES('Teresa Silva', 'teresa@gmail.com');
```

obs. como nos casos acima, não preciso inserir o número no id.

# inserir registro na tabela tb_participacao
```
INSERT INTO tb_participacao(participante_id, atividade_id) VALUES(1, 1);
INSERT INTO tb_participacao(participante_id, atividade_id) VALUES(1, 2);
INSERT INTO tb_participacao(participante_id, atividade_id) VALUES(2, 1);
INSERT INTO tb_participacao(participante_id, atividade_id) VALUES(3, 1);
INSERT INTO tb_participacao(participante_id, atividade_id) VALUES(3, 2);
INSERT INTO tb_participacao(participante_id, atividade_id) VALUES(4, 2);
```



