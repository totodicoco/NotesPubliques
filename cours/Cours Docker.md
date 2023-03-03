## Plan

1.  Introduction à Docker : qu'est-ce qu'un conteneur, comment il diffère d'une machine virtuelle, pourquoi utiliser Docker
2.  Installation de Docker sur différentes plateformes (Windows, Mac, Linux)
3.  Les commandes de base de Docker : pull, run, stop, start, etc.
4.  Utilisation de Dockerfiles pour créer des images de conteneurs personnalisées
5.  Utilisation de Docker Compose pour définir et exécuter des applications multi-conteneurs
6.  Utilisation de Docker Swarm ou Kubernetes pour gérer des clusters de conteneurs
7.  Utilisation de Docker dans les pipelines de déploiement continu
8.  Utilisation de Docker pour les tests et les développements d'applications
9.  Utilisation de Docker dans les environnements de production
10.  Conclusion : bénéfices de l'utilisation de Docker, tendances futures.

## Introduction à Docker
  
Définition de Docker : Docker est un logiciel qui permet d'empaqueter une application avec toutes ses dépendances, et de les exécuter de manière isolée dans un environnement standardisé.

Différence entre les conteneurs et les machines virtuelles : les conteneurs utilisent le système d'exploitation hôte, tandis que les machines virtuelles utilisent leur propre système d'exploitation. Les conteneurs sont donc plus légers et plus rapides à démarrer.

Pourquoi utiliser Docker : Docker permet de faciliter le déploiement d'applications, de les rendre plus portables et de garantir une meilleure reproductibilité des environnements.

## Définition
Docker est un logiciel open-source qui facilite la création, le déploiement et l'exécution d'applications dans des conteneurs logiciels. Un conteneur est un environnement logiciel qui contient tout ce dont une application a besoin pour fonctionner, comme les bibliothèques, les outils de développement et les fichiers de configuration. Les conteneurs sont similaires aux machines virtuelles, mais ils sont beaucoup plus légers et plus rapides à démarrer, car ils partagent les ressources de l'hôte sur lequel ils sont exécutés.

L'un des avantages clés de Docker est la portabilité. Les conteneurs Docker peuvent être créés sur un ordinateur de développement, testés sur un autre et déployés sur un serveur de production, tout en étant sûrs qu'ils fonctionneront de la même manière dans chaque environnement.

Docker utilise des images pour construire les conteneurs. Une image est une capture de l'état d'une application, qui comprend tous les fichiers et les configurations nécessaires pour exécuter l'application. Il est possible de créer des images à partir de conteneurs existants ou de construire des images à partir de zéro en utilisant un script de construction appelé "Dockerfile".

Docker permet également de gérer facilement les conteneurs à l'échelle. On peut utiliser des outils tels que Docker Compose pour définir des applications multi-conteneurs et les déployer sur plusieurs serveurs, ou utiliser des services tels que Kubernetes pour gérer les conteneurs à l'échelle de production.

En résumé, Docker est un système de virtualisation de conteneurs qui permet de créer, de déployer et d'exécuter des applications de manière efficiente et portable.


Chapitre installation
@TODO

## chapitre 3 Les commandes de bases

3.  Les commandes de base de Docker :
    -   Introduction : le client Docker permet de gérer les conteneurs sur une machine hôte. Les commandes de base les plus couramment utilisées sont :
        -   `docker pull` : pour télécharger une image de conteneur depuis un registre
        -   `docker run` : pour exécuter un conteneur à partir d'une image
        -   `docker stop` : pour arrêter un conteneur en cours d'exécution
        -   `docker start` : pour démarrer un conteneur qui a été arrêté
        -   `docker rm` : pour supprimer un conteneur
        -   `docker images` : pour lister les images de conteneurs locales
        -   `docker ps` : pour lister les conteneurs en cours d'exécution
    -   Exemples :
        -   Télécharger l'image de conteneur `nginx` en utilisant la commande `docker pull nginx`
        -   Exécuter un conteneur à partir de l'image `nginx` en utilisant la commande `docker run --name mynginx -p 80:80 -d nginx`
        -   Arrêter un conteneur en cours d'exécution en utilisant la commande `docker stop mynginx`
        -   Démarrer un conteneur qui a été arrêté en utilisant la commande `docker start mynginx`
        -   Supprimer un conteneur en utilisant la commande `docker rm mynginx`
        -   Lister les images de conteneurs locales en utilisant la commande `docker images`
        -   Lister les conteneurs en cours d'exécution en utilisant la commande `docker ps`
    -   Pratique :
        -   Télécharger une image de conteneur
        -   Exécuter un conteneur à partir de l'image téléchargée
        -   Arrêter et supprimer le conteneur
        -   Lister les images de conteneurs locales et les conteneurs en cours d'exécution
## Principales commandes
### Installation
```bash
apt install docker.io

```
### Liste des commandes
```
root@leojag:~# docker

Usage:  docker [OPTIONS] COMMAND

A self-sufficient runtime for containers

Options:
      --config string      Location of client config files (default "/root/.docker")
  -c, --context string     Name of the context to use to connect to the daemon (overrides DOCKER_HOST env var and default context set with "docker context use")
  -D, --debug              Enable debug mode
  -H, --host list          Daemon socket(s) to connect to
  -l, --log-level string   Set the logging level ("debug"|"info"|"warn"|"error"|"fatal") (default "info")
      --tls                Use TLS; implied by --tlsverify
      --tlscacert string   Trust certs signed only by this CA (default "/root/.docker/ca.pem")
      --tlscert string     Path to TLS certificate file (default "/root/.docker/cert.pem")
      --tlskey string      Path to TLS key file (default "/root/.docker/key.pem")
      --tlsverify          Use TLS and verify the remote
  -v, --version            Print version information and quit

Management Commands:
  builder     Manage builds
  config      Manage Docker configs
  container   Manage containers
  context     Manage contexts
  image       Manage images
  manifest    Manage Docker image manifests and manifest lists
  network     Manage networks
  node        Manage Swarm nodes
  plugin      Manage plugins
  secret      Manage Docker secrets
  service     Manage services
  stack       Manage Docker stacks
  swarm       Manage Swarm
  system      Manage Docker
  trust       Manage trust on Docker images
  volume      Manage volumes

Commands:
  attach      Attach local standard input, output, and error streams to a running container
  build       Build an image from a Dockerfile
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  events      Get real time events from the server
  exec        Run a command in a running container
  export      Export a container's filesystem as a tar archive
  history     Show the history of an image
  images      List images
  import      Import the contents from a tarball to create a filesystem image
  info        Display system-wide information
  inspect     Return low-level information on Docker objects
  kill        Kill one or more running containers
  load        Load an image from a tar archive or STDIN
  login       Log in to a Docker registry
  logout      Log out from a Docker registry
  logs        Fetch the logs of a container
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  ps          List containers
  pull        Pull an image or a repository from a registry
  push        Push an image or a repository to a registry
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  rmi         Remove one or more images
  run         Run a command in a new container
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  search      Search the Docker Hub for images
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  version     Show the Docker version information
  wait        Block until one or more containers stop, then print their exit codes

Run 'docker COMMAND --help' for more information on a command.

To get more help with docker, check out our guides at https://docs.docker.com/go/guides/

```
### Commandes les plus couramment utilisées

-   `docker run` : cette commande permet de lancer un conteneur à partir d'une image. Par exemple, pour lancer un conteneur à partir de l'image Ubuntu, vous pourriez utiliser la commande `docker run ubuntu`.
    
-   `docker ps` : cette commande permet de voir les conteneurs en cours d'exécution sur le système. Elle affiche des informations telles que l'ID du conteneur, le nom, le statut, etc.
    
-   `docker stop` : cette commande permet d'arrêter un conteneur en cours d'exécution. Par exemple, pour arrêter un conteneur avec l'ID `abc123`, vous pourriez utiliser la commande `docker stop abc123`.
    
-   `docker images` : cette commande permet de voir les images disponibles sur le système. Elle affiche des informations telles que l'ID de l'image, le nom, la taille, etc.
    
-   `docker pull` : cette commande permet de télécharger une image depuis un registre Docker. Par exemple, pour télécharger l'image Ubuntu, vous pourriez utiliser la commande `docker pull ubuntu`.
    
-   `docker build` : cette commande permet de construire une image à partir d'un fichier "Dockerfile". Par exemple, si vous avez un fichier "Dockerfile" dans le répertoire courant, vous pourriez utiliser la commande `docker build .` pour construire une image à partir de ce fichier.
    
-   `docker push` : cette commande permet de pousser une image vers un registre Docker. Par exemple, si vous avez construit une image et que vous voulez la partager avec d'autres, vous pourriez utiliser la commande `docker push nom_de_l_image`
    
-   `docker exec` : cette commande permet d'exécuter une commande dans un conteneur en cours d'exécution. Par exemple, pour ouvrir une session shell dans un conteneur avec l'ID `abc123`, vous pourriez utiliser la commande `docker exec -it abc123 /bin/bash`.

### Voir les conteneurs qui tournent
```bash
docker ps
```
### Voir tous les conteneurs
```bash
docker ps -a
```
### Descendre une image
```
docker pull alpine:latest
	latest: Pulling from library/alpine
	8921db27df28: Pull complete 
		Digest: sha256:f271e74b17ced29b915d351685fd4644785c6d1559dd1f2d4189a5e851ef753a
	Status: Downloaded newer image for alpine:latest
	docker.io/library/alpine:latest
```

### Lancer un conteneur
```
root@leojag:~# docker run alpine
```
### Lancer en mode interactif un conteneur
```
root@leojag:~# docker run -di --name mon_instance_d_alpine alpine
root@leojag:~# docker exec -ti mon_instance sh
/ # ps #Nous sommes dans le contener on voit qu'il n'y a presque pas de processus
PID   USER     TIME  COMMAND
    1 root      0:00 /bin/sh
   13 root      0:00 sh
   19 root      0:00 ps
/ # exit
 
root@leojag:~# docker stop mon_instance 
mon_instance

```
L'option -name permet de fixer un nom sans quoi docker met des noms au hazard.
### chapitre 4 Utilisation de Dockerfiles

4.  Utilisation de Dockerfiles pour créer des images de conteneurs personnalisées :
    -   Introduction : un Dockerfile est un script qui décrit les étapes pour construire une image de conteneur. Il contient des instructions telles que quelles paquets installer, quelles variables d'environnement configurer, quels fichiers copier, etc.
    -   Les instructions couramment utilisées dans un Dockerfile :
        -   `FROM` : spécifie l'image de base à utiliser pour construire l'image personnalisée
        -   `RUN` : exécute une commande pour installer des paquets ou configurer des variables d'environnement
        -   `COPY` : copie des fichiers de la machine hôte vers le conteneur
        -   `ENV` : définit des variables d'environnement
        -   `CMD` : spécifie la commande à exécuter lorsque le conteneur est démarré
    -   Exemples :
        -   Un exemple de Dockerfile qui crée une image de conteneur qui exécute un serveur web Nginx FROM nginx:latest COPY index.html /usr/share/nginx/html CMD ["nginx", "-g", "daemon off;"]
    -   Pratique :
        -   Créez un fichier Dockerfile
        -   Utilisez les instructions pour construire une image personnalisée
        -   Exécutez un conteneur à partir de l'image personnalisée

## chapitre 5 Utilisation de Docker Compose

5.  Utilisation de Docker Compose pour définir et exécuter des applications multi-conteneurs :
    -   Introduction : Docker Compose est un outil qui permet de définir et de gérer des applications multi-conteneurs en utilisant un fichier de configuration. Il facilite la création, la mise à l'échelle et la gestion des conteneurs d'une application complexe.
    -   Les concepts clés de Docker Compose :
        -   Services : les conteneurs d'une application qui sont gérés par Compose
        -   Compose file : le fichier de configuration qui décrit les services, les réseaux et les volumes pour une application
        -   Réseaux : les réseaux virtuels qui sont créés pour connecter les services entre eux
        -   Volumes : les données partagées entre les services
    -   Exemples :
        -   Un exemple de Compose file qui définit une application web qui utilise un service Nginx et un service MySQL version: '3' services: web: build: . ports: - "8000:8000" depends_on: - db db: image: mysql:5.7 environment: MYSQL_ROOT_PASSWORD: example
    -   Pratique :
        -   Créez un fichier Compose file
        -   Utilisez les instructions pour définir une application multi-conteneurs
        -   Exécutez l'application en utilisant les commandes de Compose

## Chapitre 6
Nous allons aborder les raisons pour lesquelles il peut être nécessaire d'utiliser un système de gestion de clusters et les différentes situations où cela peut être bénéfique.

Les raisons pour lesquelles vous pourriez vouloir utiliser un système de gestion de clusters incluent :

    La haute disponibilité : en utilisant un cluster, vous pouvez vous assurer que votre application est toujours disponible même si un conteneur ou un noeud échoue.
    La scalabilité : les clusters permettent de facilement ajouter ou retirer des conteneurs pour répondre aux besoins changeants de votre application.
    La répartition de charge : en répartissant les conteneurs sur plusieurs noeuds, vous pouvez équilibrer la charge sur votre système pour éviter les surcharges.

Il y a plusieurs systèmes de gestion de clusters disponibles, tels que Docker Swarm et Kubernetes. Ces systèmes sont utilisés pour gérer des clusters de conteneurs en production. Ils permettent de décrire les déploiements, les services et les volumes de manière déclarative.

Il y a aussi des avantages et des limites à utiliser un système de gestion de clusters.

Avantages de l'utilisation de système de gestion de clusters :

    Scalabilité : les clusters de conteneurs permettent de facilement ajouter ou retirer des noeuds pour répondre aux besoins changeants de l'application. Cela permet d'optimiser les ressources utilisées et de gérer les pics de charge.

    Disponibilité : en utilisant des clusters, les applications peuvent être mises à l'échelle pour gérer les échecs de noeuds individuels. Les systèmes de gestion de clusters permettent également de mettre en place des stratégies de tolérance de panne pour maintenir la disponibilité de l'application.

    Flexibilité : les systèmes de gestion de clusters permettent de déployer des applications sur différents types de noeuds, y compris des environnements cloud et edge, offrant ainsi plus de flexibilité pour les déploiements.

    Automatisation : les systèmes de gestion de clusters automatisent de nombreuses tâches liées à la gestion des clusters, telles que le déploiement, la mise à l'échelle et la surveillance.

Limites de l'utilisation de système de gestion de clusters :

    Complexité : la gestion de clusters peut être complexe et nécessiter des compétences spécifiques pour la mise en place et la maintenance des systèmes.

    Portabilité : Les clusters de conteneurs peuvent être déployés sur différentes plateformes, notamment les clouds publics, privés et hybrides, ce qui permet une portabilité accrue.

Limites :

    La complexité accrue : Gérer un cluster de conteneurs est plus complexe que de gérer un conteneur unique. Il y a plus de composants à surveiller et configurer, et les erreurs peuvent être plus difficiles à identifier et à résoudre.
    La nécessité de compétences supplémentaires : Les administrateurs de systèmes et les développeurs doivent avoir des compétences supplémentaires pour gérer et déployer efficacement des clusters de conteneurs.
    Les coûts supplémentaires : Les systèmes de gestion de clusters peuvent avoir des coûts supplémentaires liés à la gestion et à l'exploitation des ressources supplémentaires nécessaires pour gérer le cluster.
    La consommation de ressources : Les clusters de conteneurs peuvent consommer plus de ressources système que les conteneurs individuels, ce qui peut nécessiter des mises à niveau matérielles coûteuses.

Il est important de noter que la gestion de clusters de conteneurs peut être complexe et nécessiter une expertise technique élevée. Il peut également y avoir des coûts supplémentaires liés à l'utilisation d'un système de gestion de clusters,

mais ces coûts peuvent être considérablement réduits grâce à l'automatisation et à l'optimisation des ressources.

Il est également important de choisir un système de gestion de clusters adapté à vos besoins spécifiques en termes de scalabilité, de disponibilité et de flexibilité. Il existe de nombreux systèmes de gestion de clusters différents, tels que Kubernetes, Docker Swarm, Apache Mesos, etc. chacun ayant ses propres avantages et limites.

En résumé, les systèmes de gestion de clusters de conteneurs peuvent offrir une scalabilité, une disponibilité et une flexibilité accrues pour les applications, mais ils peuvent également être plus complexes à gérer et nécessiter des compétences supplémentaires et des coûts supplémentaires. Il est important de peser les avantages et les limites pour déterminer si l'utilisation d'un système de gestion de clusters est appropriée pour votre environnement.