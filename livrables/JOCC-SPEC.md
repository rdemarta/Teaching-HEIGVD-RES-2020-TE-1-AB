# Calculator Protocol
# Protocole JOCC 0.9 

**Auteur: Robin Demarta (`robin.demarta@heig-vd.ch`)**

## Introduction

Dans ce document nous allons spécifier le protocole de communation client-serveur pour JOCC (Jokes give hOpe during the Covid Confinement period). Un serveur aura le rôle de stocker les jokes leur note, l'auteur, les catégories et toute autres données relatives à JOCC. Un client, lui, pourra envoyer des requêtes aux serveurs pour lire ou envoyer des jokes.

## Choix

- L'échelle des notes d'évaluation des jokes est fixée de 1 à 10 afin d'assurer une homogénéité pour tous les servers. Le client ne sera donc pas perturbé s'il change souvent de serveur.
- Les catégories ne seront formées que de cararactères alphanumériques minuscules afin d'éviter la redondance.
- Le choix du nombre de jokes les plus récentes, les mieux évaluées ou les classement utilisateurs à afficher est laissé libre aux servers.
- Pour des raisons de respect de la vie privée, l'identification des utilisateurs ne se fera pas en stockant leur adresse IP mais en leur laissant choisir un pseudonyme au début de la communication.

## Spécifications techniques

- Port: 12000
- Encodage: UTF-8
- Initie et termine la communication: le client
- La commande d'initialisation `HI <pseudo>` requiert directement le nom d'utilisateur afin d'éviter un envoie-réponse de plus.

### Etat

Le protocole est avec état: afin d'identifier les utilisateurs, ces derniers doivent choisir un pseudonyme (au début de la communation) qui sera stocké pendant la durée du dialogue. Ceci permet une bonne extensibilité en cas d'ajout de fonctionnalités nécessitant une authentification. Ce pseudonyme pourra être stocké à long terme si l'utilisateur insère une nouvelle joke, par exemple.

### Commandes client

**Notation des paramètres:** `<X>` signifie que X est obligatoire et `[Y]` que Y est facultatif.

- `HI <pseudo>`, initie la connection avec le serveur en spécifiant le pseudo avec lequel l'utilisateur faire ses actions.
- `SND <texte d'une joke> [catégorie]`, envoie une nouvelle joke au serveur avec une éventuelle catégorie.
- `GET <x> [catégorie]`, demande x jokes au server, provenant d'une éventuelle catégorie.
- `GET BST [catégorie]`, demande les meilleures jokes, avec une éventuelle catégorie.
- `GET RCT`, demande les jokes les plus récentes.
- `EVL <id> <note>`, permet d'évaluer (de 1 à 10) la joke ayant l'identifiant `id`.
- `SCR EVL`, affiche les utilisateur avec les jokes les mieux notées.
- `SCR CNT`, affiche les utilisateur ayant posté le plus de jokes.
- `BYE`, termine la connexion.

### Commandes serveur
- `READY <pseudo>`, confirme au client ayant annoncé `HI <pseudo>` que la connection est établie, le pseudo stocké (ce dernier est retourné à l'utilisateur pour confirmation), et que le serveur est prêt à recevoir des requêtes.
- `<id> - <contenu>`, format d'une joke envoyée à l'utilisateur (une joke par ligne).
- `<x> - <pseudo> <y>`, format d'affichage des utilisateurs dans un classement, où x est la position dans le classement et y le nombre lié au classement (e.g. le nombre de jokes postées ou l'id de la joke la mieux notée)

### Exemple
- Client: `HI robin`
- Serveur: `READY robin`
- Client: `GET 3`
- Serveur:
```
1 - Super joke 1
3 - Funny thing
49 - Nice joke
```
- Client: `BYE`

## Remarques

Aucune.