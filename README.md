# group32
This github repository contains the 3 jupyter notbook files we created for the final project of the course 'knowledge and data'.

###Explanation about the 3 notebooks###

- OntologyCreator.ipynb
This .ipynb file creates one big turtle file. It uses multiple functions we created, as can be seen in this file. If you run the function named 'Main' it takes one integer as input. This integer is the amount of films you want the data from. If you give the function '500' as input it will take the first 500 films from the data.linkedmdb.org ontology. It will fetch the movie IDs and names from the IMDB database and store them as triples. It will also created triples of all the actors, writers and directors that played a role in these movies. A triple with the predicate 'worked with' will be created between the people the worked together in the same movie. It prints "still going" after each 50 iterations to show the function is still working. At the end it uses the functions 'gettingAge' and 'gettingAge' To determine what the age is of a person (actor, director or writer) is. The function does this by sending a Query to dbpedia, this query fetches the DataofBirth from dbpedia for this person. The remaining code in this function calculates in what age-group the person belongs, based on his DateofBirth. 

- ShortestPath_Application.ipynb
This .ipynb uses Query's on the ontology we created with ontologyCreator.ipynb. This ontology is loaded in stardog so we can use a SPARQL query on it. The function named findShortestPaths had 2 values as input named 'startName' and 'targetName'. By using a query on the localhost it gets the data about the people the startName has worked with, after this the function again uses a query on the localhost to get the data about the people these persons has worked with. It keeps looping in that manner untill the targetName is found. This path is the shortest path between the startName and the TargetName and is returned as output. If these are for example 2 paths with a length of 4, then both paths are returned as output. The classes and codes at the last code block in this notebook are created so we have a user interface where the function ontologyCreator will be used in. 

- OntologyVisualization.ipynb
This function uses the ontology we created in the ontologyCreator.ipynb file to create a visualization of the ontology with the actors, directors and writers within the movies. Each node in the graph is a person, a link between two persons means they have worked together. The nodes are given a color based on their age-group we collected by querying to dbpedia.org.  The colors in the graph mean the following:
ageGroup-1 = 0-24,    Color: Yellow
ageGroup-2 = 25-40,   Color: Blue
ageGroup-3 = 41-55,   Color: Green
ageGroup-4 = 56-70,   Color: Red
ageGroup-5 = 71-85,   Color: Brown
ageGroup-6 = 85+      Color: Black
