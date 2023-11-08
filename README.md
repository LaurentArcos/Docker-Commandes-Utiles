# Commandes Docker utiles

Voir fichier cycle_container_docker.pngssudo

## Créer une image

```sudo docker build -t dockerchallenges01 .```

sudo docker build -t {nom souhaité tout en miniscules et attaché} .

Le point pour indiquer qu'on lance dans le répertoire où on se situe

## Voir la liste des images créées

```sudo docker images```

ou

```sudo docker image ls```

## Supprimer une image

```sudo docker image rm dockerchallenges01```

## Renommer une image

ici exemple renommer pour publier sur dockerhub avec nom du compte avant par convention :

```sudo docker tag my-json-server:v1.0 jeremyoclock/my-json-server:v1.0```

## Lancer le docker en éxécutant Dockerfile

```sudo docker run -i -t -p 3000:3000```

ou

```sudo docker run --rm -d -p 80:3000 laurentarcos/my-json-server:v1.0```

## Voir la liste des Docker actifs

```sudo docker ps``` (affiche le nom du conteneur dans la colone NAMES)

## Voir la liste des Docker même ceux inactifs

```sudo docker ps -a```

## Stopper le conteneur actif

```sudo docker stop {nom du fichier}```

## lancer le conteneur actif

```sudo docker start {nom du fichier}```

## Supprimer un conteneur

```sudo docker rm {nom du fichier}```

il faudra alors relancer ```sudo docker run -i -t -p 3000:3000``` pour en créer un nouveau

## Se connecter à DockerHub

```sudo docker login```

login = laurentarcos
mdp = mdphabituel

## Publier sur DockerHub

```sudo docker push laurentarcos/my-json-server:v1.0```

</br>

## Installation d'un projet frontend et backend avec Docker Compose

### Initialiser un projet en installant les technologies à utiliser : 

``` terminal
npx create-react-app frontend --template typescript
npm init --yes (dans dossier backend)
npm i -D typescript @types/express @types/node
npm i express
npx tsc --init
npm i -D concurrently nodemon

```

pour challenge S02E02 :

```terminal
npm create vite@latest my-vue-app -- --template react-ts
npm init --yes (dans dossier backend)
npm i -D typescript @types/node
npx tsc --init
npm i -D concurrently nodemon directus
```

### puis les commandes Docker Compose

```sudo docker compose up``` 

pour ne pas avoir tous les log au chargement : 
```sudo docker compose up -d``` 

ou pour ne voir que les logs du conteneur frontend par exemple
```sudo docker compose up -d frontend``` 

Pour stopper un conteneur :

```sudo docker compose stop``` (start / restart)

Pour start/restart un conteneur :

```sudo docker compose start / restart``` 

Pour supprimer un conteneur :

```sudo docker compose down```
