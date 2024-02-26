# exercicio rede social

# inserir dados nas tabelas


# inserir dados na tabela tb_usuario

```
INSERT INTO tb_usuario(nome, email, nascimento, website, genero, telefone, foto_de_perfil_id) VALUES('João Silva', 'joao@gmail.com', '1991-10-15', null, 'M', null, null);
INSERT INTO tb_usuario(nome, email, nascimento, website, genero, telefone, foto_de_perfil_id) VALUES('Maria Alice', 'alice@gmail.com', '1999-04-15', null, 'F', null, null);
INSERT INTO tb_usuario(nome, email, nascimento, website, genero, telefone, foto_de_perfil_id) VALUES('Carlos Alves', 'carlos@yahoo.com', null, null, 'M', '99777-8383', null);
INSERT INTO tb_usuario(nome, email, nascimento, website, genero, telefone, foto_de_perfil_id) VALUES('Ana Clara', 'clara@gmail.com', '1997-01-23', 'blog.clara.com', 'F', '88181-2820', null);
```

# inserir dados na tabela tb_seguidores
```
INSERT INTO tb_seguidores(seguidor_id, seguido_id) VALUES(1, 3);
INSERT INTO tb_seguidores(seguidor_id, seguido_id) VALUES(1, 4);
INSERT INTO tb_seguidores(seguidor_id, seguido_id) VALUES(3, 4);
INSERT INTO tb_seguidores(seguidor_id, seguido_id) VALUES(2, 4);
```

# inserir dados na tabela tb_postagem
```
INSERT INTO tb_postagem(texto, instante, autor_id) VALUES('#partiu festa!', TIMESTAMP WITH TIME ZONE '2017-08-09T22:34:20Z', 4);
INSERT INTO tb_postagem(texto, instante, autor_id) VALUES('Bom dia pessoal!', TIMESTAMP WITH TIME ZONE '2017-08-10T10:50:00Z', 4);
```

obs. a data em formato utc fica com 3hs a mais do que a hora que o professor tem no exercício. 

obs. utc é o padrao do meridiano é a hora que esta la e o formato de escrever com T e Z.

obs. para funcionar em todos os banco de dados, usar o texto TIMESTAMP WITH TIME ZONE.


# inserir dados na tabela tb_album
```
INSERT INTO tb_album(titulo, instante_de_postagem, usuario_id) VALUES('Férias de verão', TIMESTAMP WITH TIME ZONE '2017-01-13T13:50:13Z', 3);
```

# inserir dados na tabela tb_foto
```
INSERT INTO tb_foto(uri, intante_de_postagem, postagem_id, usuario_id, album_id) VALUES('http://dominio;com/praia1.jpg', TIMESTAMP WITH TIME ZONE'2017-01-10T13:30:14Z', null, 3, 1);
INSERT INTO tb_foto(uri, intante_de_postagem, postagem_id, usuario_id, album_id) VALUES('http://dominio;com/praia2.jpg', TIMESTAMP WITH TIME ZONE'2017-01-10T13:31:12Z', null, 3, 1);
```


