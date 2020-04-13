# quick_wp EN -version
A docker-compose setup to clone any time you want a new install of WP



Uses the visiblevc/wordpress-starter image.

## Initialization

### Prerequisites

* You'll need docker installed... google is your friend. Don't worry too much about learning docker at this point.
* You need git installed, again, google is your friend!


### Create a new project
`git clone https://github.com/aljagne/quick_wp MyNewProjectName`

### Start up the container
CD into your MyNewProjectName and run the following command:

`docker-compose up -d`

You can see the status of the container with this command:
`docker ps`

It typically takes a minute or two to spin up everything depending on your machine and your internet connection.

## Access 

WP User: root

WP Password: root

DB Password: root

DB Connection Port: 9001

PhpMyAdmin Port: 22222

Finally access the site at:
http://localhost:8080

### Connect into the container

To get a command line in the container:

`docker exec -it $(docker ps -lq) /bin/bash`

WP-CLI is installed and you can run all the standard commands on a running container.

The ./app directory contains your WP install. You can copy files in after starting the container, etc. using your normal host OS/File manager, etc.

The ./plugins directory is where I put my local plugin zip files I want to install for this project. I can install them with the following command on a bash command line as noted above:

`wp plugin install /home/admin/plugins/myplugin.zip`

You can import a DB like this:

`docker-compose exec wordpress /bin/bash "wp db import $(find /data/*.sql | head -n 1) --allow-root"`


# quick_wp FR -version
Un docker-composer setup pour cloner à chaque fois que vous voulez une nouvelle installation de WP



Utilise l'image de démarrage visiblevc/wordpress-starter.

## Initialisation

### Conditions préalables

* Vous aurez besoin d'installer le docker... google est votre ami. Ne vous inquiétez pas trop de l'apprentissage de Docker à ce stade.
* Vous avez besoin que git soit installé, encore une fois, google est votre ami !


### Créer un nouveau projet
`git clone https://github.com/aljagne/quick_wp MyNewProjectName`

### Démarrer le conteneur
CD dans votre MyNewProjectName et exécutez la commande suivante :

`docker-composer -d`

Cette commande vous permet de voir le statut du conteneur :
`docker ps`

Il faut en général une minute ou deux pour tout faire tourner, selon votre machine et votre connexion Internet.

## Accès 

Utilisateur WP : root

Mot de passe WP : root

Mot de passe DB : root

Port de connexion de la DB : 9001

Port de PhpMyAdmin : 22222

Enfin, accédez au site à l'adresse :
http://localhost:8080

### Se connecter dans le conteneur

Pour obtenir une ligne de commande dans le conteneur :

`docker exec -it $(docker ps -lq) /bin/bash`

WP-CLI est installé et vous pouvez exécuter toutes les commandes standard sur un conteneur en cours d'exécution.

Le répertoire ./app contient votre installation de WP. Vous pouvez y copier des fichiers après avoir démarré le conteneur, etc. en utilisant votre système d'exploitation/gestionnaire de fichiers hôte normal, etc.

Le répertoire ./plugins est l'endroit où je place les fichiers zip de mes plugins locaux que je veux installer pour ce projet. Je peux les installer avec la commande suivante sur une ligne de commande bash comme indiqué ci-dessus :

wp plugin install /home/admin/plugins/myplugin.zip

Vous pouvez importer une DB comme celle-ci :

`docker-compose exec wordpress /bin/bash "wp db import $(find /data/*.sql | head -n 1) --allow-root"`
