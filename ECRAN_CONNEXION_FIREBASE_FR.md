# Écran de connexion Firebase ajouté

Le fichier `app/src/main/java/mr/gstmt/app/FirebaseSignInScreen.kt` contient un composable Kotlin pour connexion e-mail/mot de passe et demande de réinitialisation. Il affiche un message explicite lorsque Firebase n'est pas initialisé.

## Important
- Ce composable est un composant prêt à intégrer, mais n'est pas encore branché à la navigation de `MainActivity`.
- Il nécessite le vrai fichier `app/google-services.json`, le plugin Google Services Gradle compatible et l'activation de la méthode E-mail/Mot de passe dans Firebase Authentication.
- Aucun écran d'inscription publique n'est prévu : les comptes doivent être créés par l'administration dans un environnement sécurisé.
- Après connexion, vérifier les rôles/permissions via des custom claims définis côté serveur et des règles Firestore testées. Le callback UID/e-mail n'est pas une preuve de rôle.
- La réinitialisation dépend de l'activation de la méthode e-mail/mot de passe et de la configuration e-mail du projet Firebase.
- Les messages d'erreur sont génériques afin de limiter la révélation de l'existence d'un compte.

## Tests requis
1. Firebase non configuré : l'écran doit afficher les instructions au lieu de planter.
2. Connexion valide et invalide.
3. Réinitialisation avec adresse valide/invalide, sans divulguer l'existence du compte.
4. Déconnexion, expiration/révocation de session et accès refusé pour chaque rôle.
5. Vérifier que les règles Firestore bloquent tout accès non autorisé.

Ce code n'a pas été compilé dans cet environnement. Il doit être synchronisé et testé dans Android Studio avant toute utilisation.
