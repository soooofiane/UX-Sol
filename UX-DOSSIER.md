# GrannyHelp — Dossier UX / concept 01

**Signature : Petits services. Grands liens.**

## Livrables et consultation

Ouvrir `index.html` dans un navigateur. Le dossier fonctionne localement, sans installation et sans accès réseau. Trois onglets donnent accès aux maquettes interactives, à la charte et aux parcours UX. Les fichiers `styles.css`, `app.js` et les trois images doivent rester à côté de `index.html`.

Le prototype contient les écrans de bienvenue, inscription en trois étapes, connexion, récupération de mot de passe, accueil selon le rôle, filtres, profil d’un jeune, demande ponctuelle ou hebdomadaire, confirmation d’envoi, services, messages, profil utilisateur et gestion d’un proche. Les interactions sont simulées en mémoire et se réinitialisent au rechargement ou au changement d’écran dans le sélecteur du dossier. Aucun compte, message, e-mail ou paiement réel n’est créé.

## 1. Proposition de service

GrannyHelp met en relation des jeunes et des personnes âgées pour des services à domicile : courses, ménage, petit bricolage et informatique. Le rapprochement repose sur trois critères combinés : proximité, disponibilité et type de service. Le besoin peut être ponctuel ou régulier.

La personne âgée peut utiliser l’application elle-même ou être accompagnée. Dans ce deuxième cas, l’accompagnateur possède le compte, organise les demandes et échange avec le jeune, avec l’accord de la personne âgée. Le bénéficiaire reste clairement identifié dans l’interface.

Le pourboire est libre, facultatif et remis directement entre le jeune et la personne âgée. Aucun montant recommandé, paiement intégré ou pourboire imposé n’est prévu dans cette conception.

## 2. Charte graphique

### Marque et logo

- Nom retenu : **GrannyHelp**, cohérent avec le dossier de projet et le logo fourni.
- Signature principale : **Petits services. Grands liens.**
- Promesse d’accueil : **Un petit coup de main. Un grand sourire.**
- Logo : réutilisation de `Group 1.png`, sans déformation ni recoloration.
- Zone de protection : au moins un quart de la hauteur du logo sur chaque côté.
- Fond : clair et uni. Conserver les proportions 240 × 97. Éviter l’agrandissement au-delà de la résolution native ; obtenir un original vectoriel pour la production et l’impression.

### Palette

| Couleur | Hex | Usage |
| --- | --- | --- |
| Soleil | #F6DC69 | Action principale, petits accents |
| Forêt | #28382F | Texte principal, pictogrammes |
| Papier | #F8F7F1 | Fond général |
| Sauge | #E8EDDF | Contexte accompagnateur, surfaces secondaires |
| Pêche | #F3DFD2 | Avatars et illustrations |
| Crème jaune | #FFF2BE | Carte d’accueil et illustrations |
| Texte secondaire | #687066 | Explications et informations secondaires |

Le jaune est un fond d’action, associé à du texte forêt. Une couleur ne porte jamais seule un état : conserver les libellés, coches et contours de sélection.

### Typographie et composants

Georgia Regular / Italic pour les titres et la signature ; Segoe UI Regular / Semibold pour les contenus et formulaires, avec Arial en repli. Ces polices système permettent une consultation hors ligne.

Pour l’application finale : corps 16–18 px, labels 14–16 px, titres 28–36 px, cibles tactiles au moins 44 × 44 px. Le dossier présente des téléphones à échelle compacte ; les tailles visibles ne constituent pas une validation d’accessibilité en production. Prévoir agrandissement du texte, navigation clavier, lecture d’écran, contrastes et tests sur appareils réels.

Bouton principal jaune arrondi ; bouton secondaire à contour ; champs avec label permanent ; une action principale par étape. Grille d’espacement de 4/8 px ; rayons de 12–16 px pour les composants et de 16–20 px pour les cartes.

### Icônes, illustrations et personnage

Pictogrammes linéaires de 24 × 24, extrémités arrondies, toujours accompagnés d’un texte pour les catégories : sac de courses, ménage, outil, ordinateur. Les SVG sont intégrés à la maquette et éditables dans `app.js`.

Les assets `Frame.png` et `an-old-grann-sitting-on-her-couc-removebg-preview-2 1.png` sont réutilisés tels quels. Leur trait libre, les aplats doux et les scènes de rencontre donnent la direction stylistique. Éviter les clichés de dépendance : présenter les aînés comme acteurs de leur quotidien.

Personnage proposé : **Mamie**, complice des premiers pas et des confirmations. Une démonstration de mouvement est disponible dans la charte : deux légères bascules, déclenchées au clic. Il s’agit de l’illustration entière animée, pas d’un personnage articulé. Le réglage `prefers-reduced-motion` désactive le mouvement.

Ton : vouvoiement, phrases concrètes et chaleureuses. Dire « Un coup de main pour… », « Pour Madeleine », « En attente de réponse ». Expliquer les erreurs près du champ concerné et proposer une suite possible aux résultats vides.

## 3. Personas — hypothèses à valider

### Lucas, 22 ans — jeune volontaire

Étudiant, disponible entre ses cours. Il veut rendre service et rencontrer ses voisins. Il craint les trajets trop longs, les besoins imprécis et les horaires incompatibles. Il attend des demandes proches, un type de service clair, une durée, une fréquence et un contact facile. Citation de travail : « J’ai deux heures de libres. Autant les rendre utiles. »

### Camille, 46 ans — accompagnatrice

Fille de Madeleine, elle organise une partie de l’aide quotidienne. Elle veut simplifier la coordination sans décider à la place de sa mère. Elle craint de multiplier les échanges et de confondre son compte avec celui du bénéficiaire. Elle attend un contexte « Pour Madeleine », une gestion du proche et un suivi des demandes. Citation de travail : « Je veux organiser l’aide sans tout faire à sa place. »

### Madeleine, 78 ans — bénéficiaire sans smartphone

Elle veut rester chez elle, conserver ses habitudes et faire des rencontres. Elle a besoin d’aide ponctuelle, mais n’utilise pas l’app. Elle souhaite savoir qui vient, quand et pour quoi. Elle peut donner son accord par un échange avec Camille et reste libre du pourboire. Citation de travail : « Un peu d’aide, oui. Et j’aime bien faire connaissance. »

Ces profils sont fictifs et ne résultent pas d’entretiens réalisés.

## 4. Architecture des premiers écrans

1. **Bienvenue** : logo, illustration de rencontre, promesse, bouton « C’est parti ! », lien connexion.
2. **Inscription / rôle** : jeune, accompagnateur ou personne qui cherche de l’aide.
3. **Inscription / compte** : prénom, e-mail, mot de passe, charte d’entraide.
4. **Inscription / contexte** : quartier ; pour le jeune, service et disponibilité ; pour l’accompagnateur, prénom du proche, lien et accord.
5. **Connexion** : e-mail et mot de passe, affichage du mot de passe, récupération, inscription.
6. **Accueil** : salutation, quartier, bénéficiaire si nécessaire, quatre catégories de service, voisin ou demande à proximité, rappel du pourboire.
7. **Recherche** : filtres combinés service / distance / disponibilité, tri du plus proche au plus éloigné, résultat vide explicatif.
8. **Profil et demande** : compétences, distance et disponibilité ; service ponctuel ou chaque semaine, date, heure et précisions.
9. **Suivi** : demande en attente, accès aux messages. L’acceptation par l’autre partie et la clôture restent à développer.

### Trois parcours

**Jeune :** bienvenue → rôle jeune → compte → quartier / service / disponibilité → besoins proches → détail → proposer son aide → attente et échanges.

**Accompagnateur :** bienvenue → rôle accompagnateur → compte → proche / quartier / accord → accueil « Pour Madeleine » → jeune compatible → demande → attente et échanges.

**Aîné autonome :** bienvenue → recherche d’aide → compte → quartier → accueil personnel → jeune compatible → demande → attente et échanges.

Les filtres s’appliquent aux exemples de profils. La saisie d’une ville change le contexte affiché, sans géocodage réel ; les distances restent fictives.

## 5. Storyboard — « Des courses. Et bien plus. »

| Scène | Situation et action | Intention de conception |
| --- | --- | --- |
| 1. Le besoin apparaît | Madeleine manque de quelques courses. Elle appelle Camille. | Le besoin peut naître en dehors de l’app. |
| 2. Camille prend le relais | Avec son accord, Camille inscrit Madeleine comme proche. | Aucun smartphone n’est nécessaire pour le bénéficiaire. |
| 3. Le bon voisin | Camille filtre les courses à moins d’un kilomètre. Lucas est disponible. | Proximité, service et disponibilité guident la rencontre. |
| 4. On se met d’accord | Camille décrit le besoin ; Lucas et elle fixent le créneau et la durée. | Une demande envoyée n’est pas encore un rendez-vous confirmé. |
| 5. La rencontre | Lucas apporte les courses. Madeleine l’accueille et ils échangent. | Le service est aussi une occasion de lien social. |
| 6. Chacun reste libre | Madeleine peut donner un pourboire à Lucas. Ils peuvent prévoir un prochain service. | Pourboire facultatif et récurrence choisie ensemble. |

Les six scènes sont également représentées visuellement dans l’onglet « Les parcours UX ». Confirmation et clôture décrivent le parcours cible ; elles ne sont pas simulées comme des réponses réelles dans la maquette.

## 6. User Journey Mapping — Camille

Objectif : organiser un premier service pour Madeleine tout en préservant ses décisions.

| Étape | Action | Émotion supposée | Difficulté | Réponse UX | Indicateur proposé |
| --- | --- | --- | --- | --- | --- |
| Besoin | Échanger avec Madeleine | Préoccupation | Pas d’accès à l’app | Parcours accompagnateur explicite | Compréhension du rôle |
| Inscription | Créer son compte et renseigner le proche | Prudence | Confusion utilisateur / bénéficiaire | Contexte « Pour Madeleine », accord | Fin d’inscription, hésitations |
| Recherche | Filtrer les jeunes disponibles | Espoir | Aucun résultat compatible | Trois filtres, explication des résultats vides | Temps jusqu’au profil pertinent |
| Organisation | Envoyer le besoin et convenir du créneau | Soulagement | Incertitude sur la confirmation | Statut en attente, conversation | Délai jusqu’à un accord |
| Rencontre | Lucas rend service à Madeleine | Confiance | Retard ou besoin mal expliqué | Détails du service et contact convenu | Réalisation et difficultés |
| Après | Décider de la suite | Satisfaction | Pourboire perçu comme obligatoire | Mention facultative, récurrence choisie | Compréhension et réutilisation |

Les émotions et indicateurs sont des hypothèses, pas des résultats mesurés. Le dossier visuel ajoute la ligne des points de contact à cette carte.

## 7. Value Proposition Canvas

### Segment principal : l’accompagnateur

| Profil utilisateur | Proposition de valeur correspondante |
| --- | --- |
| **Jobs :** trouver une aide locale, coordonner le créneau et la récurrence, organiser les échanges pour son proche. | **Produits et services :** mise en relation locale, fiche bénéficiaire, filtres, demandes, messages et suivi. |
| **Pains :** disponibilité inconnue, informations à répéter, proche écarté des décisions, attente financière floue. | **Pain relievers :** filtres combinés, contexte du bénéficiaire conservé, accord explicite, distinction demande / confirmation, pourboire libre hors app. |
| **Gains :** aide compatible, moins de coordination, relation humaine régulière. | **Gain creators :** profils locaux, échanges avant la rencontre, service ponctuel ou hebdomadaire, accompagnement sans compte pour l’aîné. |

### Segment jeune

- Jobs : rendre service près de chez soi sur ses temps libres, choisir des tâches adaptées.
- Pains : trajets trop longs, demandes vagues, horaires incompatibles.
- Gains : utilité sociale, rencontres, liberté d’engagement.
- Produit : liste de besoins locaux, filtres, détail du service, échange avec le bénéficiaire ou son accompagnateur.
- Réduction des difficultés : distance et créneau visibles, besoin décrit avant de proposer son aide.
- Création de bénéfices : engagement ponctuel ou régulier choisi ; relation humaine ; pourboire éventuel et libre.

### Valeur pour le bénéficiaire

Recevoir de l’aide à domicile sans obligation numérique, garder un rôle dans l’organisation, savoir qui vient et créer un lien de voisinage. Le rôle de l’accompagnateur réduit la friction numérique ; la confirmation du besoin avec le proche préserve son choix.

## 8. Validation proposée

Faire tester le prototype par deux jeunes, deux accompagnateurs et deux aînés. Les effectifs sont un point de départ qualitatif, pas une validation statistique.

- Choisir le bon rôle sans aide.
- Créer une demande pour un proche et identifier clairement son bénéficiaire.
- Trouver un profil selon la distance, le service et la disponibilité.
- Distinguer une demande envoyée d’un service confirmé.
- Expliquer avec ses mots que le pourboire est facultatif et direct.
- Tester oralement le scénario sans app : qui vient, quand, pour quoi, comment changer d’avis.
- Observer les difficultés de lecture et de manipulation sur téléphone réel.

## 9. Périmètre et références

Sources de conception : votre description fonctionnelle et les trois PNG fournis. Le lien Google Slides a été tenté mais son contenu n’était pas accessible depuis l’environnement ; ce dossier suit les rubriques demandées sans prétendre reproduire les slides.

Lien fourni : https://docs.google.com/presentation/d/1yWPZvnijux1hJAAn0oZUZKrYFC4eGGZmVhtrltuJ2dI/edit

À développer après validation de la direction : authentification réelle, persistance, disponibilité réelle, géocodage, confirmation par l’autre personne, modification / annulation et clôture d’un service. Ce livrable est une conception et un prototype, pas une application de mise en relation opérationnelle.
