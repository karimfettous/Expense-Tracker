# Expense Tracker — Cahier des besoins

## 1. Presentation du projet

Expense Tracker est une application permettant d'enregistrer et de gerer ses depenses quotidiennes.

L'objectif est de disposer d'un outil simple pour suivre ses depenses, les organiser par categories et conserver un historique de ses transactions.

L'application sera developpee progressivement afin de commencer par les fonctionnalites essentielles, puis d'ajouter des fonctionnalites complementaires.

## 2. Objectifs du projet

L'application doit permettre a l'utilisateur de :

- Enregistrer ses depenses quotidiennes.
- Organiser ses depenses par categories.
- Consulter les depenses enregistrees.
- Modifier les informations d'une depense.
- Supprimer une depense.
- Personnaliser les categories de depenses.
- Conserver ses donnees apres la fermeture de l'application.

A terme, l'application permettra egalement d'analyser les depenses et de consulter les depenses passees.

## 3. Informations d'une depense

Chaque depense comportera les informations suivantes :

| Information | Obligatoire | Description |
|---|---|---|
| Identifiant unique | Oui | Identifiant genere automatiquement par l'application. Il permet de distinguer chaque depense et de la retrouver pour la consulter, la modifier ou la supprimer. |
| Montant | Oui | Somme depensee, exprimee en dinars algeriens (DA). Le montant doit etre strictement positif. |
| Categorie | Oui | Categorie existante a laquelle appartient la depense. |
| Date | Oui | Date du jour, generee automatiquement par l'application au moment de l'ajout de la depense. |
| Heure | Oui | Heure generee automatiquement par l'application au moment de l'ajout de la depense. |
| Description | Non | Precisons facultatives sur la depense. Elle peut rester vide. |

### 3.1. Regles concernant les informations d'une depense

- L'identifiant unique est genere automatiquement et ne peut pas etre modifie par l'utilisateur.
- Le montant est saisi par l'utilisateur et doit etre strictement superieur a zero.
- La categorie est choisie par l'utilisateur parmi les categories disponibles.
- La date est remplie automatiquement lors de l'ajout de la depense.
- L'heure est remplie automatiquement lors de l'ajout de la depense.
- L'utilisateur ne peut pas modifier la date ni l'heure apres leur generation.
- La description est facultative et peut contenir des informations complementaires sur la depense.
- Chaque depense doit etre associee a une categorie existante.

Exemple de description : « Dejeuner au restaurant ».

## 4. Gestion des categories

### 4.1. Categories initiales

Au demarrage, l'application proposera une liste predefinie de categories.

Categories initiales :

- Nourriture
- Transport
- Logement et factures
- Etudes
- Shopping
- Loisirs
- Sante
- Autres

L'utilisateur choisira une categorie dans cette liste lorsqu'il enregistrera une depense.

### 4.2. Informations d'une categorie

Chaque categorie comportera les informations suivantes :

| Information | Obligatoire | Description |
|---|---|---|
| Identifiant unique | Oui | Identifiant genere automatiquement par l'application. Il ne peut pas etre modifie par l'utilisateur. |
| Nom | Oui | Nom de la categorie. Les categories initiales sont fournies par l'application et l'utilisateur pourra creer ses propres categories. |

Aucune description supplementaire ne sera associee aux categories dans la premiere version.

### 4.3. Personnalisation des categories

La personnalisation des categories fait partie des fonctionnalites prioritaires.

L'utilisateur pourra :

- Ajouter une categorie.
- Modifier le nom d'une categorie.
- Supprimer une categorie, sous reserve des regles de suppression definies dans ce document.

L'identifiant unique d'une categorie sera genere automatiquement et ne pourra pas etre modifie par l'utilisateur.

### 4.4. Interdiction des categories en double

Pour le moment, deux categories ne pourront pas porter le meme nom.

Lorsqu'un utilisateur essaiera de creer une categorie dont le nom existe deja, l'application devra refuser la creation afin d'eviter les doublons.

Cette regle s'appliquera egalement aux categories initiales fournies par l'application.

La comparaison des noms devra etre definie pendant la conception technique, notamment pour determiner le traitement des majuscules et des minuscules.

### 4.5. Suppression d'une categorie

Une categorie ne pourra etre supprimee que si aucune depense ne lui est associee.

Si une ou plusieurs depenses sont associees a une categorie, l'application interdira sa suppression.

L'utilisateur devra d'abord supprimer manuellement toutes les depenses associees a cette categorie.

Une fois toutes les depenses supprimees, l'utilisateur pourra supprimer la categorie.

Si l'utilisateur tente de supprimer une categorie qui contient encore des depenses, l'application devra afficher le message suivant :

« Impossible de supprimer cette categorie, car des depenses y sont associees. Supprimez d'abord ces depenses. »

L'application ne devra jamais supprimer automatiquement les depenses associees lors de la suppression d'une categorie.

## 5. Relation entre les depenses et les categories

Les depenses et les categories entretiennent une relation.

Les regles suivantes devront etre respectees :

- Une depense doit etre associee a une seule categorie.
- Une categorie peut etre associee a plusieurs depenses.
- Une depense ne peut pas etre associee a une categorie inexistante.
- Une categorie ne peut pas etre supprimee tant que des depenses lui sont associees.
- La suppression d'une depense ne doit pas entrainer la suppression de sa categorie.
- La modification du nom d'une categorie ne doit pas supprimer les depenses qui lui sont associees.

Cette relation devra etre prise en compte lors de la conception de la base de donnees.

## 6. Fonctionnalites prioritaires

Les fonctionnalites suivantes seront developpees en priorite.

### 6.1. Ajouter une depense

L'utilisateur pourra enregistrer une nouvelle depense en renseignant :

- Le montant.
- La categorie.
- Une description facultative.

L'application devra automatiquement generer :

- L'identifiant unique de la depense.
- La date d'ajout.
- L'heure d'ajout.

Avant l'enregistrement, l'application devra verifier la validite des informations saisies.

Le montant devra etre strictement positif et la categorie devra exister.

### 6.2. Consulter les depenses

L'utilisateur pourra afficher les depenses enregistrees et consulter les informations associees a chacune d'elles.

Les informations affichees comprendront notamment :

- Le montant.
- La categorie.
- La date.
- L'heure.
- La description, lorsqu'elle est renseignee.

### 6.3. Modifier une depense

L'utilisateur pourra modifier une depense existante.

La modification devra concerner uniquement la depense selectionnee, sans creer inutilement une nouvelle depense.

L'utilisateur pourra modifier :

- Le montant.
- La categorie.
- La description.

L'identifiant unique, la date et l'heure generees lors de la creation ne pourront pas etre modifies par l'utilisateur.

### 6.4. Supprimer une depense

L'utilisateur pourra supprimer une depense enregistree.

La suppression devra concerner uniquement la depense selectionnee.

L'application devra eviter les suppressions accidentelles, par exemple en demandant une confirmation avant la suppression definitive.

La suppression d'une depense ne devra pas entrainer la suppression de la categorie associee.

### 6.5. Personnaliser les categories

L'utilisateur pourra ajouter des categories personnalisees, modifier le nom des categories existantes et supprimer les categories qui ne sont associees a aucune depense.

L'application devra respecter les regles de gestion des categories, notamment l'interdiction des doublons et la protection des categories encore utilisees.

## 7. Fonctionnalites secondaires

Les fonctionnalites suivantes seront envisagees dans une version ulterieure.

### 7.1. Calculer les depenses

L'application pourra calculer :

- Le montant total de toutes les depenses.
- Le montant total depense pendant une journee.
- Le montant total depense pendant un mois.
- Le montant total depense dans chaque categorie.

### 7.2. Consulter les depenses passees

L'utilisateur pourra retrouver les depenses enregistrees precedemment et consulter son historique.

Ces fonctionnalites permettront d'analyser les habitudes de consommation.

## 8. Conservation des donnees

Les depenses et les categories devront etre conservees apres la fermeture de l'application et le redemarrage de l'ordinateur.

Les donnees devront pouvoir etre retrouvees lors d'une prochaine utilisation.

Une solution de stockage persistant sera donc necessaire.

Le projet utilisera Django et une base de donnees SQLite pour commencer.

La configuration et l'organisation de la base de donnees seront definies pendant la phase de conception technique.

## 9. Regles de gestion

L'application devra respecter les regles suivantes :

1. Chaque depense possede un identifiant unique genere automatiquement.
2. Chaque categorie possede un identifiant unique genere automatiquement.
3. Une depense doit posseder un montant, une categorie, une date et une heure.
4. La description d'une depense est facultative.
5. Le montant d'une depense doit etre strictement positif.
6. La date et l'heure sont generees automatiquement lors de l'ajout d'une depense et ne sont pas modifiables par l'utilisateur.
7. Une depense doit etre associee a une categorie existante.
8. Une modification doit mettre a jour la depense existante.
9. Une suppression doit concerner uniquement la depense selectionnee.
10. Deux categories ne peuvent pas porter le meme nom.
11. Une categorie ne peut pas etre supprimee tant que des depenses lui sont associees.
12. L'application doit afficher un message explicatif lorsqu'une suppression de categorie est refusee en raison de depenses associees.
13. La suppression d'une depense ne doit pas supprimer sa categorie.
14. La modification du nom d'une categorie ne doit pas supprimer les depenses associees.
15. Les donnees doivent etre conservees apres la fermeture de l'application.
16. Les donnees saisies doivent etre validees avant leur enregistrement.

## 10. Limites de la premiere version

La premiere version se concentrera sur :

- L'ajout des depenses.
- La consultation des depenses.
- La modification des depenses.
- La suppression des depenses.
- La gestion des categories.
- La validation des donnees.
- La conservation des donnees dans la base de donnees.

Les calculs avances et les fonctionnalites supplementaires d'analyse seront developpes ulterieurement.

Les fonctionnalites pourront evoluer au fur et a mesure de l'avancement du projet.

## 11. Evolutions possibles

Des ameliorations pourront etre envisagees apres la premiere version :

- Afficher des graphiques de depenses.
- Ajouter des filtres de recherche.
- Definir un budget mensuel.
- Comparer les depenses entre plusieurs mois.
- Ajouter une gestion des revenus.
- Exporter les donnees.
- Ameliorer l'interface utilisateur.

Ces evolutions ne font pas partie des priorites immediates.

## 12. Choix technologique et motivations

Le projet sera developpe avec Django, un framework Python pour le developpement web.

Ce choix repose sur les raisons suivantes :

- Je suis deja familier avec Django, car j'ai deja developpe un site avec ce framework.
- Django facilite la mise en place de fonctionnalites comme l'authentification, la connexion, la deconnexion et l'interface d'administration.
- Je suis deja familier avec l'utilisation de SQLite pour conserver les donnees.
- Je souhaite continuer a progresser en developpement web et realiser un projet que je pourrai presenter sur mon GitHub.
- Je prefere developper ce projet avec un framework que je connais deja, plutot que de choisir une solution Python plus simple mais moins adaptee a mes objectifs d'apprentissage.

Le projet sera donc realise progressivement avec Django, Python et SQLite.

Les details de l'architecture, de la structure des applications Django et de l'organisation du code seront definis au cours de la conception technique.