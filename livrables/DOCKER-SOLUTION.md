# Rendu de l'exercice Docker 

**Auteur: Robin Demarta (`robin.demarta@heig-vd.ch`)**

## Compte rendu

- Lorsqu'on lance un serveur, nous sommes accueillis avec un message contenant le port utilisé: **2020**
- Pour communiquer avec le serveur, j'ai d'abord voulu lancer un container oliechti/faq avec `docker run -i oliechti/faq /bin/bash`.
- Pour trouver l'adresse IP du serveur: `docker inspect <container>`. Mais il n'y avait pas netcat.
- J'ai donc relancé le serveur avec le paramètre `-p 2020:2020` et `-p 2021:2020` pour le deuxième, afin de pouvoir communiquer via netcat depuis ma machine (`-p 2120:2020` afin de ne pas entrer en colision avec le premier serveur, le port 2020 du 2ème est bindé avec le 2021 de ma machine).

## Capture d'écran

Assurez-vous que vous avez placé la capture d'écran dans un fichier nommé `CAPTURE-RES.png`.

## Remarques

Aucune.