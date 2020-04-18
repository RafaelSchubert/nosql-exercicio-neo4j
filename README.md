# nosql-exercicio-neo4j
Exercícios de Neo4j da disciplina de Bancos de Dados Não-Relacionais do curso de Especialização em Data Science, turma 2, pela FURB.

-----

• Exercise 1.1: Retrieve all nodes from the database.
> MATCH (vertice) RETURN vertice;

• Exercise 1.2: Examine the data model for the graph.
> CALL db.schema.visualization();
Nota: o material de consulta menciona como "CALL db.schema;". No entanto, isso mudou.

• Exercise 1.3: Retrieve all Person nodes.
> MATCH (vertice:Person) RETURN vertice;

• Exercise 1.4: Retrieve all Movie nodes.
> MATCH (vertice:Movie) RETURN vertice;

-----

• Exercise 2.1: Retrieve all movies that were released in a specific year.
> MATCH (filme:Movie) WHERE filme.released = <ano> RETURN filme;
Ou:
> MATCH (filme:Movie {released: <ano>}) RETURN filme;
Por exemplo:
> MATCH (filme:Movie) WHERE filme.released = 2000 RETURN filme;
Ou:
> MATCH (filme:Movie {released: 2000}) RETURN filme;

• Exercise 2.2: View the retrieved results as a table.


• Exercise 2.3: Query the database for all property keys.
> CALL db.propertyKeys;
Ou:
> CALL db.propertyKeys();

• Exercise 2.4: Retrieve all Movies released in a specific year, returning their titles.
> MATCH (filme:Movie {released: <ano>}) RETURN filme.title AS Titulo;
Por exemplo:
> MATCH (filme:Movie {released: 1998}) RETURN filme.title AS Titulo;

• Exercise 2.5: Display title, released, and tagline values for every Movie node in the graph.
> MATCH (filme:Movie) RETURN filme.title, filme.released, filme.tagline;

• Exercise 2.6: Display more user-friendly headers in the table
> MATCH (filme:Movie) RETURN filme.title AS Titulo, filme.released AS Lancamento, filme.tagline AS Slogan;

-----

• Exercise 3.1: Display the schema of the database.

• Exercise 3.2: Retrieve all people who wrote the movie Speed Racer.

• Exercise 3.3: Retrieve all movies that are connected to the person, Tom Hanks.

• Exercise 3.4: Retrieve information about the relationships Tom Hanks had with the set of movies retrieved earlier.

• Exercise 3.5: Retrieve information about the roles that Tom Hanks acted in.

-----
