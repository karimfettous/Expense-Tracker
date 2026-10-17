# Expense Tracker — Decisions du projet

## 1. Identifiant automatique

Chaque depense et chaque categorie possede un identifiant unique genere automatiquement par l'application.

- L'identifiant est attribue lors de la creation.
- L'utilisateur ne peut pas modifier cet identifiant.
- L'identifiant permet de retrouver precisement une depense ou une categorie pour effectuer les operations necessaires.

## 2. Relation entre les depenses et les categories

Chaque depense doit obligatoirement etre associee a une categorie existante.

- Une depense ne peut pas exister sans categorie.
- Une categorie peut etre associee a plusieurs depenses.
- La suppression d'une depense ne doit pas supprimer sa categorie.
- La modification du nom d'une categorie ne doit pas supprimer les depenses qui lui sont associees.

## 3. Suppression des categories

Une categorie ne peut pas etre supprimee tant qu'au moins une depense lui est associee.

Si l'utilisateur tente de supprimer une categorie non vide, l'application doit refuser la suppression et afficher le message suivant :

« Impossible de supprimer cette categorie, car des depenses y sont associees. Supprimez d'abord ces depenses. »

L'utilisateur doit supprimer manuellement toutes les depenses associees avant de pouvoir supprimer la categorie.

L'application ne doit jamais supprimer automatiquement les depenses lors de la suppression d'une categorie.

## 4. Categories sans doublons

Deux categories ne peuvent pas porter le meme nom.

Lorsqu'un utilisateur tente de creer une categorie dont le nom existe deja, l'application doit refuser sa creation afin d'eviter les doublons.

## 5. Perimetre de la version 1

La premiere version se concentre exclusivement sur la gestion des depenses et des categories.

### Fonctionnalites incluses

- Ajouter une depense.
- Consulter les depenses enregistrees.
- Modifier une depense existante.
- Supprimer une depense.
- Ajouter une categorie.
- Modifier le nom d'une categorie.
- Supprimer une categorie uniquement si elle ne contient aucune depense.
- Valider les donnees avant leur enregistrement.
- Conserver les donnees apres la fermeture de l'application.

### Fonctionnalites exclues de la version 1

Les fonctionnalites suivantes ne seront pas developpees dans la premiere version :

- Gestion des revenus.
- Calcul des totaux de depenses.
- Calcul des totaux journaliers, mensuels ou par categorie.
- Systeme de comptes utilisateurs.
- Inscription et authentification des utilisateurs.

Ces fonctionnalites ne font pas partie du perimetre initial du projet.

## 6. Authentification et comptes utilisateurs : plus tard

La mise en place d'un systeme de comptes utilisateurs, avec inscription, connexion et deconnexion, est reportee a une version ulterieure.

La raison de ce choix est de commencer par maitriser les fonctionnalites essentielles de gestion des depenses et des categories avant d'ajouter la gestion des utilisateurs.

Django facilitera l'ajout de l'authentification lorsque cette fonctionnalite deviendra prioritaire.

Le systeme de comptes ne doit donc pas etre implemente dans la version 1.

## 7. Choix technologiques

Le projet sera developpe avec :

- Python comme langage de programmation.
- Django comme framework web.
- SQLite comme base de donnees initiale.

Ces technologies sont choisies parce que je connais deja Django et que j'ai deja developpe un site avec ce framework.

Ce projet doit egalement me permettre de renforcer mes competences en developpement web et d'enrichir mon portfolio GitHub.

## 8. Regles generales

Les decisions suivantes doivent etre respectees pendant le developpement :

1. Chaque depense et chaque categorie possede un identifiant unique genere automatiquement.
2. Chaque depense doit toujours etre associee a une categorie existante.
3. Une categorie non vide ne peut pas etre supprimee.
4. La suppression d'une categorie ne doit jamais supprimer automatiquement ses depenses.
5. Deux categories ne peuvent pas porter le meme nom.
6. La version 1 ne comprend ni gestion des revenus, ni calcul des totaux, ni comptes utilisateurs.
7. L'authentification sera envisagee plus tard.
8. Les donnees doivent etre conservees apres la fermeture de l'application.
9. Le developpement doit se faire progressivement afin de comprendre chaque fonctionnalite implementee.

### Date et heure automatiques

J'ai choisi que la date et l'heure soient remplies automatiquement quand j'ajoute une dépense. Je ne veux pas avoir à les saisir à chaque fois, parce que je risque de les oublier ou de faire une erreur.

Par contre, il y a un inconvénient : si j'oublie d'enregistrer une dépense et que je le fais le lendemain, elle aura la date et l'heure du moment où je l'ajoute, et non celles du véritable achat. Pour la V1, j'accepte cette limite pour garder les choses simples.