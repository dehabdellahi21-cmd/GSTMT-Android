# Mise en place Firebase — Groupe Scolaire Thierno Mountaga Tall

## État exact
Le projet contient les dépendances Android Firebase Authentication et Cloud Firestore, ainsi qu'un plan de configuration. **Aucun projet Firebase n'a été créé pour l'établissement**, car cela nécessite l'accès/consentement du propriétaire. Aucun `google-services.json`, identifiant de projet, secret, compte administrateur ou donnée réelle n'a été inventé. L'authentification Firebase n'est pas encore connectée à l'interface et l'application n'est pas prête pour la production.

## Étapes dans le compte officiel de l'établissement
1. Un responsable autorisé ouvre Firebase Console et crée un projet appartenant à l'établissement. Activer la facturation seulement après examen des besoins et des coûts; vérifier les tarifs actuels avant activation.
2. Ajouter une application Android avec l'identifiant `mr.gstmt.app` (à confirmer avant toute publication, car le `applicationId` ne doit plus être changé après diffusion).
3. Télécharger le vrai fichier `google-services.json` depuis la console Firebase et le placer dans `app/google-services.json`. Ne pas le remplacer par un fichier fabriqué.
4. Suivre la documentation officielle Firebase Android pour appliquer le plugin Google Services avec une version compatible avec le Gradle/Android Gradle Plugin du projet. Faire ensuite une synchronisation Gradle et une compilation de test.
5. Dans Authentication, activer uniquement la méthode de connexion choisie par l'établissement. Pour des comptes créés par l'administration, créer les utilisateurs via une interface d'administration sécurisée ou un environnement serveur de confiance. Ne jamais embarquer une clé de compte de service dans l'application Android.
6. Configurer Firestore, publier des règles restrictives et tester les accès avec Firebase Emulator Suite avant d'ajouter des données réelles.
7. Utiliser Firebase App Check si compatible avec l'architecture finale, limiter les privilèges des administrateurs et activer des alertes de budget/usage si disponibles.

## Modèle de comptes recommandé
- `ADMIN`: administration scolaire, création/désactivation de comptes, gestion des classes et annonces.
- `TEACHER`: uniquement classes et matières assignées.
- `PARENT`: uniquement enfants explicitement associés par l'administration.
- `STUDENT`: uniquement son propre dossier et les contenus publiés pour sa classe.

Les rôles doivent être attribués par un environnement de confiance (par exemple Admin SDK côté serveur) et vérifiés dans les règles Firestore. Ne jamais permettre à un utilisateur de modifier lui-même son rôle. L'app Android ne doit jamais contenir de clé privée Admin SDK.

## Données à valider avant de construire le schéma
- Années scolaires, classes, matières et règles de notation officielles.
- Identifiants internes des élèves, enseignants et responsables légaux.
- Liens parent-enfant vérifiés par l'administration.
- Politique de conservation, correction, export et suppression des données.
- Procédure de réinitialisation et de désactivation des comptes.

## Règles de sécurité
Le fichier `docs/firebase/firestore.rules.template` est un modèle **refusant par défaut**. Il bloque toutes les lectures/écritures tant que des règles spécifiques et auditées ne sont pas conçues. Ne pas l'assouplir pour « faire fonctionner » l'app. Les règles doivent être testées en simulateur avec des comptes de chaque rôle avant déploiement.

## Confidentialité
Avant les données réelles, publier une politique accessible par URL publique et vérifier ce que Firebase et chaque SDK collectent. Compléter la section Sécurité des données Play Console selon le comportement réel de l'application. Ne pas envoyer de notes, absences, identifiants ou informations d'enfants dans des journaux non nécessaires.
