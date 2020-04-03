# Exercice 1: conception du protocole JOCC 0.9 

## Contexte

La crise liée au Coronavirus crée une situation d'isolement sans précédent, éprouvante pour de nombreuses personnes. Différents outils collaboratifs permettent aux employés, enseignants et étudiants de travailler à distance. Mais ils ne sont pas forcément adaptés pour maintenir des interactions sociales impromptues et informelles.

## Objectif

Pour cette raison, nous voulons **développer une application client-serveur** qui doit offrir les fonctionnalités suivantes:

1) On doit pouvoir déployer plusieurs **serveurs JOCC** sur un réseau TCP/IP. Chaque serveur gère ses données (pas de partage de données).

2) Les utilisateurs doivent pouvoir **envoyer des Jokes à un serveur**, en utilisant un **client** (qui peut offrir une interface graphique ou ligne de commande). Le serveur les ajoute alors à ses données, pour qu'ils soient à disposition de la communauté.

3) Les Jokes doivent pouvoir être **catégorisés** par leurs auteurs ("dark humour", "ta mère pendant le COVID...", etc.).

4) Les utilisateurs doivent pouvoir interroger le serveur et **obtenir des Jokes**. S'ils le souhaitent, ils peuvent spécifier une/des catégories parmi lesquelles choisir les Jokes.

5) Les utilisateurs doivent avoir la possibilité de donner une **évaluation** à un Joke.

6) Les utilisateurs doivent pouvoir obtenir la **liste des Jokes les mieux évalués** par la communauté, de manière globale ou par catégorie.

7) Les utilisateurs doivent pouvoir obtenir la **liste des Jokes les plus récents**.

8) Les utilisateurs doivent pouvoir obtenir le **classement des membres** de la communauté qui ont publié 1) le plus de Jokes, 2) les Jokes les mieux évalués.

**En outre, nous avons envie que la communauté puisse développer différents clients et serveurs, mais que tous soient compatibles les uns avec les autres.**

## Votre mission

Pour cette raison, on vous demande de concevoir et spécifier "**J**okes give h**O**pe during the **C**ovid **C**onfinement period" (**JOCC**), un nouveau protocole applicatif. **JOCC a pour objectif de régir les interactions entre les clients et les serveurs JOCC.**

**Attention**: vous devez vous limiter à la spécification du protocole, **en faisant bien la différence** entre ce qui appartient à cette spécification, et ce qui appartient à l'implémentation des clients et des serveurs.

**Il n'y a pas une seule manière de spécifier le protocole, et nous voulons justement voir comment vous allez faire des propositions différentes**. Par exemple, c'est à vous de décider ce que "évaluation" veut dire concrètement. C'est à vous de faire des choix et de les transcrire dans votre spécification. Prenez juste le temps d'expliquer ces choix.

**Il est possible spécifier un protocole AVEC ou SANS état**. Vous pouvez choisir le modèle que vous préférez, mais vous devez indiquer votre choix et expliquer POURQUOI votre protocole est effectivement AVEC ou SANS état.

## Marche à suivre

Vous devez livrer votre spécification dans le fichier `JOCC-SPEC.md`, qui se trouve dans le dossier `livrables`. 

* Prenez soin de bien **structurer** votre document: la **clarté** sera un point important dans l'évaluation.

* Soyez **précis** et **complets**.

* Assurez-vous que votre spécification contient **tout** ce qui permet à 2 développeurs d'implémenter un client et un serveur capables de communiquer.

* ***N'oubliez pas de committer et de pusher votre solution!! Faites le premier commit rapidement et faites des commits réguliers!!***

  
