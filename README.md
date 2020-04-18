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
Idem ao Exercício 1.2:
> CALL db.schema.visualization();

• Exercise 3.2: Retrieve all people who wrote the movie Speed Racer.
> MATCH (autor:Person)-[:WROTE]->(:Movie {title: "Speed Racer"}) RETURN autor.name;

• Exercise 3.3: Retrieve all movies that are connected to the person, Tom Hanks.
> MATCH (:Person {name: "Tom Hanks"})--(filme:Movie) RETURN filme;

• Exercise 3.4: Retrieve information about the relationships Tom Hanks had with the set of movies retrieved earlier.
> MATCH (:Person {name: "Tom Hanks"})-[relacao]-(filme:Movie) RETURN filme.title AS Titulo, type(relacao) AS Relacao;

• Exercise 3.5: Retrieve information about the roles that Tom Hanks acted in.
> MATCH (:Person {name: "Tom Hanks"})-[atuacao:ACTED_IN]-(filme:Movie) RETURN filme.title AS Filme, atuacao.roles AS Papeis;

-----

• Exercise 4.1: Retrieve all movies that Tom Cruise acted in.

• Exercise 4.2: Retrieve all people that were born in the 70’s.

• Exercise 4.3: Retrieve the actors who acted in the movie The Matrix who were born after 1960.

• Exercise 4.4: Retrieve all movies by testing the node label and a property.

• Exercise 4.5: Retrieve all people that wrote movies by testing the relationship between two nodes.

• Exercise 4.6: Retrieve all people in the graph that do not have a property.

• Exercise 4.7: Retrieve all people related to movies where the relationship has a property.

• Exercise 4.8: Retrieve all actors whose name begins with James.

• Exercise 4.9: Retrieve all all REVIEW relationships from the graph with filtered results.

• Exercise 4.10: Retrieve all people who have produced a movie, but have not directed a movie.

• Exercise 4.11: Retrieve the movies and their actors where one of the actors also directed the movie.

• Exercise 4.12: Retrieve all movies that were released in a set of years.

• Exercise 4.13: Retrieve the movies that have an actor’s role that is the name of the movie.

-----
