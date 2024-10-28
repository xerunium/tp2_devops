2-1 What are testcontainers?

Testcontainers est une bibliothèque Java facilitant les tests d'intégration en 
fournissant des services éphémère (comme des bases de données) dans 
des conteneurs Docker. Ca permet des tests isolés, 
car chaque test utilise une nouvelle instance, et donc réduit les risques de conflits 
de données.