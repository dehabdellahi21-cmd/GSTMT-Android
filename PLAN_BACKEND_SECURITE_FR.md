# Plan de réalisation du backend et des comptes administrés

## État
Ce document décrit les exigences à réaliser. Il ne signifie pas qu'un serveur existe déjà.

## Rôles
- `ADMIN`: crée, désactive et réinitialise les comptes; gère années, classes, matières et annonces.
- `TEACHER`: consulte uniquement ses classes/matières attribuées; saisit et corrige notes, présences et devoirs.
- `PARENT`: consulte uniquement les enfants qui lui sont explicitement rattachés.
- `STUDENT`: consulte uniquement son propre dossier et les contenus publiés pour sa classe.

## Parcours d'administration requis
1. Un administrateur autorisé se connecte avec authentification forte.
2. Il crée un compte en choisissant le rôle, la classe et, si nécessaire, le lien parent-enfant.
3. Un secret temporaire à usage unique est remis par un canal sûr; aucun mot de passe en clair ne doit être conservé ou envoyé par e-mail.
4. L'utilisateur définit son propre mot de passe à la première connexion.
5. L'administration peut désactiver un compte et révoquer ses sessions.
6. Les opérations sensibles sont journalisées sans enregistrer de mots de passe, jetons ou données inutiles.

## Contrôles de sécurité non négociables
- Toutes les règles d'accès sont appliquées sur le serveur, pas seulement dans l'interface Android.
- Refuser par défaut toute requête non authentifiée ou non autorisée.
- Vérifier côté serveur chaque relation utilisateur-classe-élève et parent-enfant.
- TLS obligatoire; stockage de mots de passe avec un mécanisme moderne géré par un fournisseur d'identité fiable.
- Limitation des tentatives, protection contre l'énumération de comptes, révocation de session et récupération de compte sûre.
- Sauvegardes chiffrées, accès opérateur restreints, journal d'audit et procédure d'incident.
- Ne jamais inclure de vraies notes, noms d'élèves ou identifiants dans les données de démonstration, logs ou captures publiques.

## Modèle de données minimal à valider
`users`, `students`, `guardians`, `guardian_student_links`, `teachers`, `classes`, `subjects`, `enrollments`, `grades`, `attendance_records`, `assignments`, `announcements`, `audit_events`.
Chaque table doit avoir un identifiant stable, des règles de lecture/écriture explicites et une politique de conservation définie par l'établissement.

## Choix techniques à décider avant le développement
- Hébergeur/backend et région d'hébergement.
- Fournisseur d'identité et méthode de récupération des comptes.
- Personnes habilitées à être administrateurs et procédure de transfert de responsabilité.
- Données exactes collectées, durée de conservation, suppression et traitement des demandes des familles.
- Prestataires tiers, notifications push, analytics éventuels et transferts de données.

Ne pas mettre l'application en production avant d'avoir implémenté et testé ces points.
