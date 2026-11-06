# TTDefenseShield

**Statut : prototype de recherche — code source privé, accès restreint.**

## Résumé

TTDefenseShield est un environnement de **simulation et d’analyse** destiné à la recherche en protection : détection de menaces par radiofréquence et étude de trajectoires. Il vise à tester des idées de détection dans un cadre simulé, sans équipement réel.

## Problème traité

Concevoir et comparer des approches de détection demande de pouvoir les essayer de façon répétable. Le projet fournit un cadre commun où des scénarios simulés peuvent être joués, observés et comparés.

## Architecture générale

Le projet est organisé en grands blocs :

- **Un contrat commun pour les menaces simulées** : chaque type de menace respecte la même interface logicielle, ce qui permet d’ajouter ou de remplacer un scénario sans modifier le reste du système.
- **Un bus d’événements** : les détections et les événements de simulation circulent par un canal unique, auquel les autres blocs s’abonnent.
- **Un module de profils de détection radiofréquence** : il regroupe les signatures utilisées par la détection.
- **Un tableau de bord de supervision** : il affiche les événements et l’état de la simulation.

## État d’avancement

Prototype de recherche en cours de refactorisation, afin que tous les types de menace simulés suivent le même contrat logiciel.

## Cadre d’utilisation

Le projet est mené à des fins de **recherche et de protection**. Il n’est ni distribué ni ouvert à des contributions externes.

## Ce qui n’est pas publié

Ce sujet est **sensible** et à double usage. Nous ne publions donc volontairement :

- le code source ;
- les paramètres, profils de détection et modèles ;
- la description des menaces simulées et de leurs caractéristiques ;
- les résultats de simulation.

## Collaboration

Les institutions intéressées par un partenariat de recherche peuvent ouvrir une *issue* sur ce dépôt, sans y joindre d’information confidentielle. Nous reprendrons contact par un canal privé.
