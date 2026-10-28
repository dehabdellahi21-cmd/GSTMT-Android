# Étape suivante Firebase — comptes créés par l'administration

## Ce qui est fourni
Ce dossier contient des modèles à faire relire et tester. Il ne crée pas de projet Firebase et ne contient aucun secret.

## Architecture recommandée
- Firebase Authentication : connexion par e-mail/mot de passe, si cette méthode est validée par l'établissement.
- Cloud Firestore : profils, classes, annonces, devoirs, notes et présences.
- Cloud Functions (environnement de confiance) : création de comptes par un administrateur autorisé, attribution des rôles et désactivation.
- Firebase App Check : à évaluer puis activer après tests.
- Règles Firestore : refus par défaut, autorisations limitées au rôle et aux relations parent-enfant/classe vérifiées.

## Avant toute donnée réelle
1. Le responsable crée un projet dans la console Firebase et confirme que `mr.gstmt.app` est l'identifiant Android final.
2. Ajouter l'application Android dans Firebase et télécharger le vrai `google-services.json` dans `app/`. Ne pas le publier dans un dépôt public.
3. Activer Authentication et choisir la méthode de connexion.
4. Déployer les règles et fonctions seulement après revue, tests avec Firebase Emulator Suite et validation par un développeur.
5. Créer le premier administrateur par une procédure contrôlée, jamais depuis une inscription publique libre.
6. Vérifier les journaux, sauvegardes, suppression des comptes et traitement des demandes des parents.
7. Remplacer toutes les données fictives par des données obtenues depuis le backend autorisé.

## Limite importante
Les modèles fournis ne sont pas un backend certifié. Les contrôles de rôle doivent être côté serveur et ne doivent jamais dépendre d'un champ de rôle modifiable par l'utilisateur dans son profil. Ne pas utiliser de données d'élèves avant validation de sécurité et de confidentialité.
