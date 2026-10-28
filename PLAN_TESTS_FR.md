# Plan de tests avant diffusion

## Fonctionnel
- [ ] Démarrage et navigation sur les tailles d'écran prises en charge.
- [ ] Bascule français/arabe; vérifier direction droite-à-gauche et lisibilité.
- [ ] Connexion, déconnexion, expiration de session et réinitialisation du mot de passe.
- [ ] Compte désactivé refusé; erreurs sans fuite d'informations.
- [ ] Admin crée/désactive un utilisateur et lui attribue un rôle autorisé.
- [ ] Enseignant ne modifie que les classes/matières autorisées.
- [ ] Parent ne voit que les enfants qui lui sont liés.
- [ ] Élève ne voit que ses propres notes et absences.
- [ ] Notifications et annonces n'exposent pas de données sensibles sur l'écran verrouillé.

## Sécurité et confidentialité
- [ ] Tests d'accès direct aux API avec rôles différents (accès interdit par défaut).
- [ ] Aucune clé secrète, mot de passe ou jeton dans le dépôt ou les journaux.
- [ ] Transport chiffré et règles de sauvegarde/suppression vérifiées.
- [ ] Politique de confidentialité publique et cohérente avec les SDK et données réellement collectées.
- [ ] Parcours de demande de suppression/correction défini et testé.
- [ ] Aucun dossier scolaire réel dans les captures d'écran, tests ou données de démonstration.

## Livraison Android
- [ ] Construire une version release reproductible.
- [ ] Signer un AAB avec une clé gardée en lieu sûr et sauvegardée séparément.
- [ ] Tester l'AAB sur appareils physiques et versions Android ciblées.
- [ ] Vérifier accessibilité, contrastes, RTL, rotations et erreurs réseau.
- [ ] Tester le canal interne/fermé Play avant production selon les exigences applicables au compte.
- [ ] Vérifier les formulaires Play Console à la date de soumission.
