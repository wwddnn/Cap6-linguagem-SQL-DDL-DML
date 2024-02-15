# Capítulo 6: Linguagem SQL DDL DML.
SQL é a linguagem de consulta estruturada que permite consulta ao banco de dados. 

Pode ser dividida em:

DDL usada para criar, excluir e modificar tabelas. metadados. incluir uma nova coluna na tabela, alterar o tipo de uma coluna. ou uma chave primária.

DML formular consultas e inserção, exclusão e modificação de registros nas tabelas.


> Mundo real > Modelo Conceitual > Modelo relacional(nível de design) > Modelo físico(é uma representação do banco de dados, são as minhas tabelas).

No modelo físico falamos de linguagem SQL(Structured query language-linguagem de consulta estruturada), é a linguagem padrão para acesso ao banco de dados. 

SQL tem origem na linguagem ''SEQUEL IBM'' em 1973. Depois veio o ''padrão ANSI'' para unificar as linguagens SQL. Então todos os banco de dados vão usar o SQL padrão, pode variar um pouco somente.

## SQL se divide em:
DDL: data definition language-linguagem de definição de dados. define a estrutura e esquema do banco.  Comandos que alteram a definição dos meus dados. os comando mais usados são

```
CREATE,
ALTER, 
DROP
```


DML: data manipulation language-linguagem de manipulação de dados. fazem o gerenciamento dos meus dados no banco. Comandos mais usados são 

```
SELECT, INSERT, UPDATE, DELETE, CALL
```

DCL: data control language. controle de permissão do banco. usados por DBAs. Comandos usados GRANT e REVOKE.

TCL: transaction control. gerencia as mudanças feitas por comandos DML. Comandos usados COMMIT, SAVEPOINT, ROLLBACK.

Obs. foco das próximas aulas será a DDL e DML.

Obs Vamos usar o banco de dados Postgres (sistema de gerenciamento de banco de dados relacional). é gratuito, usa padrão SQL. 

Obs assistir o vídeo de instalação do postgres (aula4 instalar postgres e pgadmin) direto no youtube da devsuperior. nele que vamos aprender a fazer nossas consultas e criação do nosso banco de dados.

















