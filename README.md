# Memo_Cmd


- DockerFile:
	- FROM image : Defines a base for your image
	- RUN command:  Executes any commands in a new layer on top of the current image and commits the result. `RUN` also has a shell form for running commands.
	- WORKDIR directory:  Sets the working directory for any `RUN`, `CMD`, `ENTRYPOINT`, `COPY`, and `ADD` instructions that follow it in the Dockerfile.
	- COPY src dest : Copies new files or directories from `<src>` and adds them to the filesystem of the container at the path `<dest>`.
	- CMD command: Lets you define the default program that is run once you start the container based on this image. Each Dockerfile only has one `CMD`, and only the last `CMD` instance is respected when multiple exist.

- Docker commands: 
	- docker logs nom-du-conteneur
	- docker build -t tagname:version .
	- docker build -t tagname:version -f DockerFile ./folderTarget
	- docker compose build
	- docker exec -it 
	- docker run --name test -d nginx:alpine
	- docker exec -it  name /bin/baqh
- Kubernetes
	- kubectl get pods -n nom-du-namespace
	- kubectl exec -it nom-du-pod -- /bin/bash
	- kubectl exec -it nom-du-pod -c nom-du-conteneur -- /bin/bash
	- kubectl logs nom-du-pod
	- kubectl top pods --all-namespaces
	- kubectl api-ressources
	- kubectl explain [RESOURCE_TYPE]  NAME
	-  kubectl describe [RESOURCE_TYPE] NAME
- Symfony:
	- logs -> /var/logs
	- installation symfony-cli:
		- curl -1sLf 'https://dl.cloudsmith.io/public/symfony/stable/setup.deb.sh' | sudo -E bash
		- sudo apt install symfony-cli

	- Installation project:
		- composer create-project symfony/skeleton:"7.1.*" demo
		- cd demo
		- composer require symfony/webapp-pack:*
		
	- Commande symfony :
		- symfony server:start -d (background)
		- symfony server:stop
		- symfony server:log
		- symfony open:local
		- php bin/console make:controller RecipeController (Créer un controller et fichiers associés)
		- php bin/console make:form (Créer un Form et fichiers associés)
		- php bin/console debug:autowiring valid (Va chercher les composant/services autowiring du container symfony qui commence par le mot clé valid)
	- Doctrine commands:
		- php bin/console make:entity Recipe (Création d'un objet ORM Recipe)
		- php bin/console make:migration (Création du script SQL pour générer les Tables liées aux objets ORM)
		- php bin/console doctrine:migrations:migrate (Exécute les scripts SQL générés par le commande au dessus)
	- debug code:
		- var_dump(var)
		- dd(var)
		- dump(var)
			

Réseau: 
sudo ngrep -d <interface> -q 'GET|POST|PUT|DELETE' tcp and port 80
sudo netstat -an | grep ':80\|:443'

Start Php server:
php -S localhost:8080 -t public
