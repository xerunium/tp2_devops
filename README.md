# 2-1 What are testcontainers?

Testcontainers est une bibliothèque Java facilitant les tests d'intégration en 
fournissant des services éphémère (comme des bases de données) dans 
des conteneurs Docker. Ca permet des tests isolés, 
car chaque test utilise une nouvelle instance, et donc réduit les risques de conflits de données.

# 2-2 Document 
on / push : 
Exécuter le workflow lors des événements push dans les branches main et develop

jobs : 
liste tout les jobs du workflow

runs on : 
Spécifie l'environnement de machine virtuelle à utiliser pour exécuter ce job.

uses: actions/checkout@v2.5.0
Cette action permet de récupérer les fichiers de votre dépôt GitHub
dans l'environnement de l'Action GitHub, pour pouvoir les utiliser dans les étapes suivantes

name :
Nom de l'étape pour la rendre plus lisible

uses: actions/setup-java@v3 :  
Utilisation de l'action setup-java dans sa version 3

run: mvn clean install : 
Commande pour construire et tester le projet

# 2-3 For what purpose do we need to push docker images?

Nous poussons des images Docker pour les déployer dans des environnements de 
production, faciliter le partage avec d'autres équipes ou services, et garantir 
la cohérence de l'application à travers différents environnements.

# Document your quality gate configuration.

mvn -B verify sonar:sonar :
Utilise Maven pour lancer la vérification (verify) du projet et exécuter le plugin SonarQube (sonar:sonar)

-Dsonar.projectKey=xerunium_tp2_devops 
clé de projet SonarCloud

-Dsonar.organization=xerunium -Dsonar.host.url=https://sonarcloud.io
nom de l'organisation

-Dsonar.login=${{ secrets.SONAR_TOKEN }}  
login grace au token enregistré

--file ./simple-api/pom.xml
Spécifie le chemin du fichier pom.xml