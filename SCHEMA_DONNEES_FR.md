# Schéma de données proposé — à valider

Collections candidates :
- `profiles/{uid}` : nom affiché, rôle non modifiable par le client, identifiant scolaire interne.
- `students/{studentId}` : classe, statut, références internes nécessaires.
- `parentStudentLinks/{linkId}` : relation parent-enfant validée par l'administration.
- `classes/{classId}` : nom de classe, année scolaire.
- `announcements/{announcementId}` : auteur, audience, contenu, dates de publication.
- `assignments/{assignmentId}` : classe, enseignant, consigne, échéance.
- `grades/{gradeId}` : élève, matière, période, note, auteur.
- `attendance/{recordId}` : élève, date, statut, auteur.

Ce schéma est indicatif. Les champs, accès, durée de conservation et règles de visibilité doivent être définis avec l'administration avant toute donnée réelle. Ne pas stocker de données médicales ou d'informations sensibles sans nécessité démontrée et protection appropriée.
