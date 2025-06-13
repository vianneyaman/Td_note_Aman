
Ce projet permet de lancer automatiquement une application WordPress avec sa base de données MySQL en utilisant Docker Compose

Explication du fichier docker-compose.yml

J'ai commencé par déclarer les conteneurs du projet. Ici, deux services : basededonnees (MySQL) et wordpres

J'ai commencé par le service basededonnees

 j'ai d'abord défini l'image MySQL qui sera utilisé par docker version 5.7

Dans les paramètres d'envivronnemnt j'ai défini le mot de passe de administrateur, le nom de la base, l’utilisateur, et son mot de passe 

 Créer par la suite un volume  bd pour sauvegarder les données MySQL même si le conteneur est supprimé

Après ça vient le deuxième service wordpress

J'ai commencé par faire une configuration selon laquelle il faut démarrer WordPress après la base de données

J'ai ensuite définin la dernière version de l'image disponible WordPress.

Le site sera accessible sur localhost:2000 

J'ai ensuite configurer WordPress pour se connecter à la base MySQL

 Crée un volume wordpress_donnees pour sauvegarder les données wordpress

 
Pour le lancement de l'application étant dans le dossier contenant le fichier "docker-compose.yml", j'ai ouvert un terminal et tapé :

docker compose up -d

Ensuite j'ai ouvert mon navigateur en entrant http://localhost:2000 et j'ai accédé à l'application wordpress me demandant de terminer une installation
et pour les conteneurs j'ai fait docker ps

 Pour arrêter l’application j'ai fait docker compose down

