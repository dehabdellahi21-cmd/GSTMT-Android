# Groupe Scolaire Thierno Mountaga Tall — projet Android starter

Projet Android natif Kotlin + Jetpack Compose pour une application scolaire bilingue français/arabe.

## Informations fournies
- Établissement : Groupe Scolaire Thierno Mountaga Tall
- Adresse : Dar El Baida, El Mina, Nouakchott, Mauritanie
- Téléphone : 32914655
- E-mail : dehabdellahi21@gmail.com
- Comptes : prévus comme comptes individuels créés par l’administration
- Logo : à créer et valider officiellement

## État actuel
- Écran d’accueil bilingue FR/AR avec bascule de langue
- Navigation locale : Accueil, Notes, Présences, Devoirs, Annonces
- Coordonnées officielles fournies visibles dans l’accueil
- Contenus de démonstration uniquement
- Dépendances Firebase Authentication et Cloud Firestore ajoutées, mais non configurées
- Aucun projet Firebase ni fichier `google-services.json` fourni; aucune authentification réelle et aucune base de données connectée
- Le projet n’a pas été compilé ni testé dans cet environnement ; aucun APK/AAB prêt à publier n’est fourni

## Ouvrir le projet
1. Installer Android Studio et un JDK 17.
2. Ouvrir ce dossier dans Android Studio.
3. Installer les composants Android SDK demandés et synchroniser Gradle.
4. Lancer sur un émulateur ou un téléphone de test.

## Étapes indispensables avant une utilisation réelle
1. Créer le logo officiel et définir les icônes/splash screen.
2. Suivre `docs/FIREBASE_MISE_EN_PLACE_FR.md` et `docs/FIREBASE_ETAT_CONFIGURATION_FR.md` pour configurer le projet Firebase appartenant à l’établissement. Les comptes et rôles ne sont pas encore connectés.
3. Appliquer les permissions côté serveur : chaque parent/élève ne doit accéder qu’aux données qui lui sont autorisées.
4. Définir la politique de confidentialité finale, la conservation et la suppression des données, et le traitement des données des mineurs.
5. Tester les scénarios de sécurité et les parcours administration/enseignant/parent/élève.
6. Préparer les captures d’écran, icône, description et fiche Google Play.
7. Générer et signer un Android App Bundle (AAB), puis compléter toutes les déclarations Play Console.

## Publication Google Play
Ce projet n’est pas publié et n’est pas encore prêt pour la production. L’acceptation par Google Play ne peut pas être garantie. Vérifier les exigences en vigueur dans Play Console au moment de la soumission, notamment cible Android, test requis selon le type de compte, sécurité des données, politique de confidentialité et contenu destiné aux enfants/mineurs. Garder la clé de signature privée.

## Documents complémentaires
- `docs/PLAN_BACKEND_SECURITE_FR.md` : exigences pour les comptes créés par l'administration et les contrôles d'accès.
- `docs/FIREBASE_MISE_EN_PLACE_FR.md` : étapes Firebase sans identifiants inventés.
- `docs/FIREBASE_ETAT_CONFIGURATION_FR.md` : checklist de configuration.
- `docs/firebase/firestore.rules.template` : règles Firestore en refus par défaut.
- `docs/FICHE_GOOGLE_PLAY_BROUILLON_FR.md` : texte proposé pour la fiche de présentation, à valider.
- `docs/PLAN_TESTS_FR.md` : liste de tests avant diffusion.

Ces documents constituent un plan de travail et ne prouvent pas que le backend, l'authentification ou les fonctions connectées ont été développés. Les textes Google Play et de confidentialité doivent refléter la version effectivement livrée.


## Suite Firebase (version de préparation)
- `docs/FIREBASE_PROCHAINES_ETAPES_FR.md` : parcours de configuration et sécurité.
- `docs/SCHEMA_DONNEES_FR.md` : schéma proposé, à valider avant usage.
- `docs/CONFIGURATION_A_FAIRE_FR.md` : informations manquantes à confirmer.
- `docs/firebase/functions/README_FR.md` : exigences pour la création de comptes côté serveur.
- `docs/firebase/firestore.rules.template` : règle initiale de refus par défaut.

Cette version n'ajoute pas de connexion Firebase active : le vrai projet Firebase, le fichier de configuration, les règles testées et les fonctions sécurisées ne sont pas disponibles. Les dépendances seules ne connectent pas l'application.


## Écran de connexion Firebase (composant à intégrer)
Le composant `FirebaseSignInScreen.kt` fournit une base pour la connexion par e-mail/mot de passe et la réinitialisation. Il n'est pas encore relié à `MainActivity`; voir `docs/ECRAN_CONNEXION_FIREBASE_FR.md`. Il n'a pas été compilé ici.


## Configuration Firebase réelle ajoutée
Le fichier `app/google-services.json` correspond au projet `gstmt-5166a` et au package `mr.gstmt.app`. Le plugin Google Services Gradle est activé. Voir `docs/FIREBASE_CONFIGURATION_RECUE_FR.md` pour les vérifications restantes. Le projet n’a pas été compilé ou testé dans cette session.


## Compilation sans ordinateur (GitHub Actions)
Cette archive contient `.github/workflows/android-build.yml`, qui lance une compilation APK de débogage sur GitHub Actions. Depuis un navigateur mobile, il faut créer un dépôt GitHub, y téléverser les fichiers du dossier du projet, puis ouvrir Actions et lancer « Build Android APK ». Le fichier APK sera proposé dans les artefacts de l'exécution. Cette méthode exige un compte GitHub et une connexion internet. L'APK debug n'est pas un paquet de publication Google Play et ne prouve pas que toutes les fonctions métier sont terminées.
