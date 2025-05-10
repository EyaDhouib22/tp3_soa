# Système de Gestion de Tâches avec GraphQL (TP3)

## Description

Ce projet est une application de gestion de tâches simple construite avec Node.js, Express, et GraphQL. Il sert d'exercice pratique (TP3) pour la matière "SoA et Microservices" (A.U. 2024/2025, Classe 4Info, Enseignant: Dr. Salah Gontara) afin de comprendre les concepts fondamentaux de la configuration et de l'utilisation de GraphQL.

L'application permet de lister, ajouter, et modifier l'état de tâches via une API GraphQL.

## Objectifs du TP

*   Comprendre comment configurer et utiliser GraphQL avec Node.js et Express.
*   Apprendre à créer un schéma GraphQL et des résolveurs pour gérer les requêtes et les mutations pour une API simple de gestion de tâches.

## Technologies Utilisées

*   **Node.js:** Environnement d'exécution JavaScript côté serveur.
*   **Express.js:** Framework web minimaliste pour Node.js.
*   **GraphQL:** Langage de requête pour API et runtime pour exécuter ces requêtes.
*   **Apollo Server:** Implémentation d'un serveur GraphQL compatible avec Express.
*   **GraphQL Tools:** Utilitaires pour la création de schémas GraphQL.
*   **body-parser** (ou `express.json()`): Middleware pour analyser le corps des requêtes HTTP.

## Prérequis

*   Node.js et npm (Node Package Manager) installés sur votre machine.
    *   Vous pouvez télécharger Node.js depuis [nodejs.org](https://nodejs.org/en/download).

## Installation et Configuration

1.  **Cloner le dépôt (si applicable) ou créer les fichiers manuellement** comme décrit dans l'énoncé du TP.
2.  Ouvrir un terminal ou une invite de commande.
3.  Naviguer jusqu'au répertoire racine du projet (par exemple, `tp-graphql`).
4.  Si vous partez de zéro et n'avez pas de `package.json`, initialisez un projet Node.js avec la commande :
    ```bash
    npm init -y
    ```
5.  Installez les dépendances nécessaires en exécutant la commande :
    ```bash
    npm install express @apollo/server body-parser @graphql-tools/schema graphql
    ```
    *(Note: `body-parser` peut être remplacé par `express.json()` intégré si vous préférez).*

## Structure du Projet (Principaux Fichiers)

*   `taskSchema.gql`: Définit le schéma GraphQL (types de données, requêtes possibles, mutations possibles).
*   `taskSchema.js`: Charge le schéma GraphQL à partir du fichier `.gql` et le rend utilisable par le serveur.
*   `taskResolver.js`: Contient la logique métier (les "résolveurs") qui spécifie comment répondre aux requêtes et exécuter les mutations définies dans le schéma.
*   `index.js`: Point d'entrée principal de l'application. Il configure le serveur Express, intègre Apollo Server, et démarre l'écoute des requêtes.
*   `package.json`: Fichier de métadonnées du projet, listant les dépendances et les scripts.

## Lancement de l'Application

1.  Depuis le répertoire racine du projet dans votre terminal, exécutez la commande :
    ```bash
    node index.js
    ```
2.  Si tout est configuré correctement, vous devriez voir un message dans la console indiquant que le serveur a démarré et sur quel port il écoute (par défaut `http://localhost:5000`). Par exemple :
    `Server started on port 5000, GraphQL at http://localhost:5000/graphql`

## Utilisation de l'API GraphQL

1.  Une fois le serveur lancé, ouvrez votre navigateur web.
2.  Accédez à l'interface graphique Apollo Studio Sandbox (ou l'outil GraphQL de votre choix) en vous rendant à l'URL spécifiée lors du démarrage du serveur, généralement :
    `http://localhost:5000/graphql`
3.  Dans cette interface, vous pouvez écrire et exécuter des requêtes GraphQL pour interagir avec l'API :
    *   **Pour récupérer des données** (par exemple, lister toutes les tâches), vous utiliserez des opérations `query`.
    *   **Pour modifier des données** (par exemple, ajouter une nouvelle tâche ou marquer une tâche comme terminée), vous utiliserez des opérations `mutation`.

    Consultez l'énoncé du TP (point 10 et suivants) pour des exemples spécifiques de requêtes à tester.

