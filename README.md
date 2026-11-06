# Bibliothèque ESST

Intégration statique en HTML5 et CSS3 des maquettes de la bibliothèque de
l’École Supérieure des Sciences et Technologies.

## Ouvrir le projet

Ouvrir **index.html** dans un navigateur. La page blanche propose deux choix
de rôle. Le projet s’ouvre directement depuis le dossier.

- **Étudiant** ouvre le catalogue et le parcours étudiant.
- **Admin** ouvre le tableau de bord et le parcours d’administration.
- Tous les logos renvoient à index.html.
- Le menu « Mon espace ESST » permet de passer d’un parcours à l’autre.

Les formulaires de connexion et d’inscription illustrent les maquettes ; ils ne
sont pas nécessaires pour entrer dans la simulation. Utiliser des informations
fictives.

## Pages créées

Les 20 écrans Figma ont chacun une page :

| Écran Figma                   | Fichier                    |
| ----------------------------- | -------------------------- |
| 01 · Accueil ESST             | accueil.html               |
| 02 · Connexion                | connexion.html             |
| 03 · Inscription              | inscription.html           |
| 04 · Catalogue                | catalogue.html             |
| 05 · Recherche                | recherche.html             |
| 06 · Détail du livre          | detail-livre.html          |
| 07 · Mes emprunts             | mes-emprunts.html          |
| 08 · Historique               | historique.html            |
| 09 · Mes réservations         | mes-reservations.html      |
| 10 · Mes favoris              | mes-favoris.html           |
| 11 · Mes avis                 | mes-avis.html              |
| 12 · Profil étudiant          | profil-etudiant.html       |
| 13 · Tableau de bord          | tableau-de-bord.html       |
| 14 · Gestion des livres       | gestion-livres.html        |
| 15 · Ajouter un livre         | ajouter-livre.html         |
| 16 · Modifier un livre        | modifier-livre.html        |
| 17 · Étudiants et enseignants | etudiants-enseignants.html |
| 18 · Rôles et permissions     | roles-permissions.html     |
| 19 · Statistiques             | statistiques.html          |
| 20 · Sécurité                 | securite.html              |

Six pages complémentaires portent le total à **26 pages HTML**.

| Usage                                          | Fichier                 |
| ---------------------------------------------- | ----------------------- |
| Page principale de choix du rôle               | index.html              |
| 21 · Composants & fenêtres du Figma            | composants.html         |
| Aide, contact et explications de la simulation | aide.html               |
| Fiche d’Introduction aux algorithmes           | detail-algorithmes.html |
| Fiche de Réseaux informatiques                 | detail-reseaux.html     |
| Fiche de Design of Everyday Things             | detail-design.html      |

Les trois dernières reprennent la disposition de la fiche Figma de Clean Code
avec le contenu du livre sélectionné, afin que toutes les cartes ouvrent le bon
ouvrage.

## Carte de navigation

| Départ                      | Destinations                                                                                                               |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Page principale · Étudiant | Catalogue                                                                                                                  |
| Page principale · Admin    | Tableau de bord                                                                                                            |
| Accueil · Spécialités       | Catalogue filtré sur la spécialité                                                                                         |
| Connexion / Inscription     | Catalogue après validation HTML des champs                                                                                 |
| Catalogue                   | Recherche, filtres, disciplines, deux présentations des cartes, fiche de chaque livre                                      |
| Fiche d’un livre            | Confirmation d’emprunt → Mes emprunts ; réservation → Mes réservations ; favori → Mes favoris ; avis → Mes avis            |
| Menu étudiant               | Accueil, Catalogue, Mes emprunts, Historique, Mes réservations, Mes favoris, Mes avis, Mon profil                          |
| Mes emprunts                | Renouvellement, signalement de retour, Historique                                                                          |
| Historique                  | Fiches des livres, Mes avis, formulaire d’avis                                                                             |
| Mes réservations            | Fiche du livre prêt à retirer, confirmation d’annulation                                                                   |
| Mes favoris                 | Fiches des livres, retrait/rétablissement local d’un favori                                                                |
| Mes avis                    | Avis publiés / À évaluer, modification, publication, suppression locale d’un avis                                          |
| Profil                      | Confirmation de modification, fenêtre de mot de passe, Accueil pour sortir de l’espace                                     |
| Menu administration         | Tableau de bord, Livres, Étudiants et enseignants, Rôles et permissions, Statistiques, Sécurité                            |
| Tableau de bord             | Ajouter un livre, fenêtres de gestion des retours et des réservations                                                      |
| Gestion des livres          | Ajouter, Modifier Clean Code, fenêtres de modification des autres ouvrages, confirmation de suppression, fiches des livres |
| Ajouter / Modifier un livre | Gestion des livres après validation HTML                                                                                   |
| Étudiants et enseignants    | Fenêtres d’ajout, de modification et de gestion d’accès                                                                    |
| Rôles et permissions        | Cases de permissions et confirmation de démonstration                                                                      |
| Sécurité                    | Formulaire de mot de passe, fenêtres d’authentification et de sessions                                                     |
| Tous les logos              | Page principale de choix du rôle                                                                                           |
| Footer                      | Catalogue, Aide, Contact, Composants & fenêtres                                                                            |

## Structure

Les spécialités affichées sont Informatique, Science et technologie, Chimie et
E-commerce. Le filtre Chimie affiche un état vide dans le catalogue de
démonstration.

Les couleurs, tailles et marges sont écrites directement dans les règles CSS.

- css/base.css : reset, typographie, focus et utilitaires.
- css/components.css : header, footer, menus, formulaires, tableaux, cartes et fenêtres.
- css/pages.css : dispositions propres aux écrans et états CSS.
- assets/logo/ESST-logo.png : copie exacte du fichier fourni, utilisée dans le
  header, le footer et le favicon, sans recadrage ni déformation.
- assets/images/ et assets/icons/ : emplacements disponibles pour de futurs
  exports d’assets.

Les 25 pages du portail partagent le même header et le même footer. Le menu latéral marque
la rubrique courante avec la classe active et aria-current. Les couvertures
typographiques visibles dans la maquette sont intégrées en texte HTML et CSS.

## Interactions et limites sans JavaScript

Les règles avec :has, :target et :checked pilotent les interactions du portail. Elles sont conservées avec les règles qui adaptent la mise en page aux petits écrans.

| Élément                                           | Alternative HTML/CSS et limite                                                                                                                                                                                                                       |
| ------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Menu mobile                                       | Case à cocher et sélecteur :checked ; navigation latérale défilante sur mobile.                                                                                                                                                                      |
| Menus déroulants et FAQ                           | Éléments details / summary natifs.                                                                                                                                                                                                                   |
| Fenêtres de confirmation                          | Fragments d’URL et :target ; fermeture par le lien × ou « Revenir ». La touche Échap et le confinement du focus ne sont pas automatisés.                                                                                                             |
| Disciplines                                       | Radios et :checked filtrent les cartes réellement présentes. Les liens d’accueil utilisent :target et :has.                                                                                                                                          |
| Pagination                                        | Deux dispositions prédéfinies des quatre mêmes ouvrages ; ce n’est pas une pagination de 1 248 livres.                                                                                                                                               |
| Recherche libre, filtres avancés, tri et périodes | Navigation vers des résultats ou explications prédéfinis. Aucune recherche arbitraire ni statistique recalculée.                                                                                                                                     |
| Favoris                                           | Retrait et rétablissement locaux avec :checked ; aucune sauvegarde persistante.                                                                                                                                                                      |
| Avis                                              | Onglets et étoiles en CSS ; masquage temporaire d’un avis avec :target. La publication mène à une confirmation de démonstration.                                                                                                                     |
| Permissions                                       | Cases natives ; leur libellé visuel suit l’état coché en CSS. Aucun accès réel n’est modifié.                                                                                                                                                        |
| Emprunts, réservations, comptes et sécurité       | Fenêtres et pages de confirmation ; les tableaux restent des exemples statiques et aucune opération réelle n’est exécutée.                                                                                                                           |
| Formulaires                                       | Contraintes HTML natives : champs requis, e-mail, longueurs, ISBN et nombres. La concordance des deux mots de passe ne peut pas être comparée sans code. Les champs de mot de passe n’ont pas de nom de soumission et ne sont pas placés dans l’URL. |
| Import d’une couverture                           | Sélecteur de fichier natif ; le nom du fichier est visible. Aucun envoi, aperçu dynamique ou contrôle effectif de la taille du fichier.                                                                                                              |
| Graphiques                                        | Barres CSS et valeurs statiques écrites dans le HTML, avec une description accessible.                                                                                                                                                               |
| Survols et focus                                  | :hover, :focus-visible, :focus-within et transitions CSS ; réduction des animations selon la préférence système.                                                                                                                                     |

Les formulaires sont des démonstrations. Ils ne créent ni compte, ni prêt, ni
e-mail, ni modification persistante. Aucun JavaScript, framework, backend, API
applicative ou base de données n’est fourni.

## Fidélité et adaptations

Le fichier Figma a été consulté dans le navigateur : ses 20 écrans et la planche
« Composants & fenêtres » ont été parcourus. Le connecteur d’extraction Figma
renvoyait une erreur ; les variables, mesures, polices et assets n’ont donc pas
pu être exportés automatiquement. Les couleurs et dimensions centralisées sont
des estimations visuelles. Une fidélité pixel-perfect certifiée nécessite les
tokens ou les exports de référence.

Les polices choisies sont Lato et Playfair Display, chargées par des liens CSS
Google Fonts. Hors ligne, Arial et Georgia prennent le relais. Ce choix de
polices n’a pas pu être confirmé dans les propriétés Figma.

La page principale présente les deux accès directs Étudiant et Admin sur fond blanc.
Le logo fourni est conservé entier. Les pages d’authentification partagent
l’en-tête et le pied de page du portail. Les textes complémentaires des trois variantes de fiche et
de l’aide ont été rédigés pour rendre le parcours cohérent. Les e-mails de
démonstration utilisent example.com.

Aucune version mobile distincte n’a été identifiée dans l’inventaire des frames
de premier niveau ; les adaptations tablette et mobile utilisent Grid, Flexbox
et des media queries. Les dates d’octobre 2026 reprennent les données des
maquettes et ne constituent pas un état actuel de la bibliothèque.

## Vérifications effectuées

- Analyse HTML5 des 25 documents, sans erreur de parsing.
- Un seul h1 par page ; absence de doublons d’identifiants.
- Vérification de tous les liens internes, fragments, images et actions de formulaire.
- Labels de tous les champs ; textes alternatifs des images.
- Header et footer identiques ; logo identique octet pour octet au fichier source.
- Absence de scripts, attributs d’événement et styles inline.
- Parsing des quatre feuilles CSS.
- Rendu navigateur des 25 pages à 1 280 px, 768 px et 320 px, sans débordement
  horizontal de document ; contrôles mobiles complémentaires à 375 px.
- Vérification des entrées Étudiant et Admin, du burger, des disciplines et de
  l’état vide, des filtres, des confirmations d’emprunt, des favoris, des onglets
  d’avis, de la pagination, des permissions et d’un formulaire de connexion.
- Les vérifications structurelles et de rendu ne remplacent pas un audit
  d’accessibilité avec des technologies d’assistance.
