# Développement Local
## Installation

Tout d'abord, [installez Docker avec docker-compose](https://docs.docker.com/compose/install/).

Ensuite, clonez le dépôt :
```
    git clone https://github.com/MartinTech63/filedrop.git
    cd filedrop
    docker-compose up -d
```
Maintenant, ouvrez votre navigateur et rendez-vous sur `http://localhost:8080`.

- Pour redémarrer les conteneurs, exécutez `docker-compose restart`.
- Pour arrêter les conteneurs, exécutez `docker-compose stop`.
- Pour déboguer le serveur NodeJS, exécutez `docker logs snapdrop_node_1`.


## Exécution locale en téléchargeant l'image depuis Docker Hub

Si Docker est installé, utilisez la commande suivante :
```
    docker pull MartinTech63/filedrop
```

Pour exécuter l'image, tapez la commande suivante (si le port 8080 est occupé par l'hôte, utilisez un autre port aléatoire <port aléatoire>:80) :
```
    docker run -d -p 8080:80 MartinTech63/filedrop
```






## Tests des fonctionnalités liées à PWA
Les applications web progressives (PWA) nécessitent que l'application soit servie sous un point de terminaison TLS correctement configuré et approuvé.

Le conteneur nginx crée un certificat d'autorité (CA) et un certificat de site web pour vous. Pour définir correctement le nom commun du certificat, vous devez modifier la variable d'environnement FQDN dans `docker/fqdn.env` pour qu'elle corresponde au nom de domaine complètement qualifié de votre poste de travail.

Si vous souhaitez tester les fonctionnalités PWA, vous devez approuver le CA du certificat pour votre déploiement local. Pour vous simplifier la tâche, vous pouvez télécharger le fichier crt à partir de `http://<Votre FQDN>:8080/ca.crt`. Installez ce certificat dans le magasin de confiance de votre système d'exploitation.
- Sous Windows, assurez-vous de l'installer dans le magasin `Autorités de certification racines de confiance`.
- Sous MacOS, double-cliquez sur le certificat CA installé dans `Accès aux clés`, développez `Confiance`, et sélectionnez `Toujours approuver` pour SSL.
- Firefox utilise son propre magasin de confiance. Pour installer le CA, accédez à `http://<Votre FQDN>:8080/ca.crt` dans Firefox. Lorsque vous y êtes invité, sélectionnez `Faire confiance à cette CA pour identifier les sites Web` et cliquez sur OK.
- Lorsque vous utilisez Chrome, vous devez redémarrer Chrome pour qu'il recharge le magasin de confiance (`chrome://restart`). De plus, après avoir installé un nouveau certificat, vous devez vider le stockage (Outils de développement -> Application -> Vider le stockage -> Vider les données du site).

Veuillez noter que les certificats (CA et certificat du serveur web) expirent après un jour.
De plus, à chaque redémarrage du conteneur nginx, de nouveaux certificats sont créés.

Le site est servi sur `https://<Votre FQDN>:443`.
    
## Notes de Déploiement
Le client s'attend à trouver le serveur à l'adresse http(s)://votre.domaine/serveur.

Lorsque vous servez le serveur Node derrière un proxy, l'en-tête `X-Forwarded-For` doit être défini par le proxy. Sinon, tous les clients servis par le proxy seront mutuellement visibles.

Par défaut, le serveur écoute sur le port 3000.

Pour un exemple de configuration nginx, consultez `docker/nginx/default.conf`.

[< Retour](/README.md)
