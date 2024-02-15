# SQL: DML (data manipulation language) - INSERT
 DML é uma sublinguagem da SQL. podemos incluir novos registros, e alterar tuplas.

Permite incluir um conjunto de registros ou tuplas em uma tabela.

Há 2 formas de se incluir esse registro:

 forma1: ordem dos atributos deve ser mantida. ex: eu tenho os campos id, nome e endereço...então meus valores v1, v2 e daí em diante tem que ser nessa ordem dos campos.

 `
INSERT INTO table_name VALUES (v1, v2, ... , vn);
`

 forma2: ordem dos atributos não precisa ser mantida. em c1, c2 etc vou dizer o nome dos campos e atributos. obs. o professor prefere essa forma para trabalhar!

`
INSERT INT table_name (c1, c2, ... , cn) VALUES (v1, v2, ... , vn);
`
