# Configuration Firebase reçue — GSTMT

Le fichier `google-services.json` fourni par l'utilisateur a été placé dans `app/google-services.json`.

Valeurs vérifiées dans le fichier :
- Projet Firebase : `gstmt-5166a`
- Numéro de projet : `1076313572414`
- Identifiant de l'application Android : `mr.gstmt.app`
- Application mobile Firebase : `1:1076313572414:android:c4c42ba022a3b552b77d6f`

Le plugin Google Services Gradle a été déclaré à la racine et activé dans le module `app`.

## À faire ensuite
1. Ouvrir ce dossier de projet dans Android Studio sur un ordinateur.
2. Laisser Gradle synchroniser et télécharger les dépendances.
3. Dans Firebase Console > Authentication > Sign-in method, activer la méthode e-mail/mot de passe si c'est bien la méthode choisie par l'établissement.
4. Tester la connexion et la réinitialisation du mot de passe avec un compte de test.
5. Définir puis tester les règles Firestore avant de stocker des informations d'élèves.

## Limites
Cette archive n'a pas été compilée ni testée dans Android Studio ici. L'intégration du fichier Firebase ne crée pas automatiquement de comptes, ne déploie pas de règles Firestore et ne garantit pas que les écrans de connexion soient déjà reliés à toutes les fonctions de l'application. Ne pas utiliser avec des données réelles d'élèves avant revue de sécurité.

`google-services.json` contient une clé API d'application mobile, pas une clé privée de compte de service. Éviter tout de même de publier le fichier et configurer les restrictions d'API appropriées dans Google Cloud si elles sont compatibles avec Firebase.
