2-1 What are testcontainers?

# Testcontainers est une bibliothèque Java facilitant les tests d'intégration en 
# fournissant des services éphémère (comme des bases de données) dans 
# des conteneurs Docker. Ca permet des tests isolés, 
# car chaque test utilise une nouvelle instance, et donc réduit les risques de conflits 
# de données.

2-2 Document 
on / push : 
# Exécuter le workflow lors des événements push dans les branches main et develop

jobs : 
# liste tout les jobs du workflow

runs on : 
# Spécifie l'environnement de machine virtuelle à utiliser pour exécuter ce job.

uses: actions/checkout@v2.5.0
# Cette action permet de récupérer les fichiers de votre dépôt GitHub
# dans l'environnement de l'Action GitHub, pour pouvoir les utiliser dans les étapes suivantes

name :
# Nom de l'étape pour la rendre plus lisible

uses: actions/setup-java@v3 :  
# Utilisation de l'action setup-java dans sa version 3

run: mvn clean install : 
# Commande pour construire et tester le projet

