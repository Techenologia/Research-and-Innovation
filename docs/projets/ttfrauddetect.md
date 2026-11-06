# TTFraudDetect

**Statut : prototype de recherche — code source privé.**

## Résumé

TTFraudDetect est une plateforme qui attribue à chaque entreprise un **score de risque de fraude** à partir de ses déclarations et de ses transactions, puis présente les résultats dans un tableau de bord destiné aux équipes de contrôle.

## Problème traité

Les équipes de contrôle ne peuvent pas examiner toutes les entreprises. L’objectif est de les aider à **prioriser** : repérer plus vite les dossiers qui méritent une vérification, et comprendre pourquoi un dossier est signalé.

## Fonctionnement général

```
Données (entreprises, déclarations, transactions)
        │
        ▼
Calcul d’un score et d’un niveau de risque
        │
        ▼
Modèle d’apprentissage automatique supervisé (gradient boosting)
        │
        ▼
Service web (API)  ──►  Tableau de bord
```

## Composants

- **Moteur de score** : calcule un score et un niveau de risque par entreprise.
- **Modèle d’apprentissage automatique** : modèle de type gradient boosting (XGBoost), entraîné pour distinguer les profils à risque.
- **API** : service web (FastAPI) qui expose les scores, les statistiques et la prédiction pour une entreprise, avec une authentification par rôles.
- **Tableau de bord** : application web (React) en quatre vues : *Dashboard* (vue d’ensemble), *Alertes*, *Analytics* et *Entreprises* (recherche par numéro d’identification fiscale, explication du score, export CSV).

## Données

Le prototype fonctionne uniquement sur un **jeu de données synthétique** généré pour les tests : environ 500 entreprises, 2 000 déclarations et 17 700 transactions. Il n’utilise aucune donnée réelle.

Les résultats obtenus sur des données synthétiques ne permettent pas de prévoir les performances en conditions réelles. Une validation sur des données réelles anonymisées, avec les autorisations nécessaires, est indispensable avant tout usage.

## Principe d’utilisation

Un score est une **aide à la décision**. Il ne constitue pas une preuve de fraude, et la décision finale appartient toujours à une personne.

## État d’avancement

- Générateur de données, moteur de score, modèle, API et tableau de bord : réalisés à l’état de prototype.
- Avant tout déploiement réel : revue de sécurité complète et cadre de protection des données.

## Pistes d’évolution

- Rapport PDF téléchargeable pour chaque entreprise.
- Déploiement en ligne.
- Base de données relationnelle (PostgreSQL) à la place des fichiers.

## Ce qui n’est pas publié

Code source, modèle entraîné, variables et seuils de détection, comptes et identifiants de démonstration. Ces éléments restent privés, car les détailler aiderait à contourner la détection.
