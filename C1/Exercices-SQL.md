**EXERCICES SQL - 10X**



- Support de cours: cf PDF Slack

- Installer base de données en local (SGBD)
  - MS SQLServer (version Express): https://www.microsoft.com/fr-fr/sql-server/sql-server-downloads#
- Installer IDE pour manipulation des données
  - DataGrip : https://www.jetbrains.com/datagrip/?fromMenu
  - SSMS (préférable si vous utilisez une MS SQL Server): https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-2017
  
- Références
  - Liste des clauses SQL et fonctions: https://www.w3schools.com/sql/default.asp



**Exercices**

Pour faire les exercices, vous devrez installer la base de données Chinook sur votre serveur local.

Pour vous aider, vous pouvez vous appuyer sur le support de cours, les références fournies, internet (si tu sais pas, Google lui le sait...) et le schéma de la base ci-dessous :



![](https://blog.stefanproell.at/wp-content/uploads/2016/01/ER.png)



*<u>Lab 01:</u>*

Ecrire les requetes qui permettent de :

- Retourner la liste de tous les **Employee**
- Retourner la liste des **Invoice** avec seulement l'ID, l'ID du client et la date
- Retourner le nom, prénom, et adresse de tous les **Customer**, la liste retournée doit comprendre 2 colonnes. La premiere avec Nom en majuscule, Prénom (exemple: "DUPONT, Jean"), la deuxième simplement le numéro de téléphone. Vous pouvez nommer les colonnes comme vous le souhaitez.
- Retourner la liste des Invoice avec comme colonnes
  - ID et total au format: <ID>(<total>) 
  - La date au format: 2019.09.10 (format ANSI)
- Retourner la liste de TOUTES les chasons (tracks) avec comme colonnes:
  - ID
  - Nom - Compositeur (exemple: "Etnia - Chico Science") si pas de compositeur ("Now Sport / NA")

*<u>Lab 02</u>*

- Retourner la liste des villes des clients en enlevant les doublons
- Retourner les 10 plus importantes factures dans l'ordre décroissant (**Invoice**)
- Retourner toutes les informations du client dont l'ID est 47
- Retourner la liste des clients qui vivent à Bordeaux, Chicago, Lisbon ou Berlin
- Retourner la liste des albums dont le titre commence par la lettre "C"
- A partir de la précédente requête, changer la clause pour afficher la liste des albums dont le titre commence par la lettre "C" et dont la deuxieme lettre n'est pas un "H"
- Retourner la liste des factures entre le 01-01-2012 et le 31-03-2013



*<u>Lab 03</u>*

- La liste des factures avec les colonnes suivantes:
  - Numéro de facture
  - Nom et prénom du client (JOINTURE)
  - Total
- Rajouter à la requete précédente:
  - Le nom de l'employé en charge du client
  - Le nom de l'artiste qui correspond à la chason qui a été achetée (aidez-vous du diagramme)
- La liste de tous les clients avec les colonnes suivantes:
  - ID
  - Nom
  - Numéro de facture

(Si un client n'a pas de facture indiquer N/A)

- Retourner la liste des chansons qui n'ont jamais été achetées
- La liste des employés avec les colonnes suivantes:
  - ID de l'employé
  - Nom
  - Email
  - Nom de son Manager
  - Email de son Manager
  - Retrouver le nom du dirigeant parmis les employés



*<u>Lab 04</u>*

- Retourner la liste des toutes les adresses, ville et pays enregistrés dans la base (employés et clients)
- La liste de toutes villes des tables Customer et Invoice, on veut voir s'il y a des doublons
- La liste des adresses clients qu'on ne retrouve pas la table Invoice
- La liste des pays communs entre les employés et les clients



<u>*Lab 05*</u>

- La liste des chansons avec les colonnes suivantes:
  - Id
  - Nom de l'artiste
  - Durée (en secondes, arrondi à la seconde supérieure)
- La liste des factures avec:
  - Id
  - date
  - Année de la facture
  - Mois de la facture (nom du mois)
  - Jour de la semaine (toujours de la facture...)
  - Les deux premiers caractères du pays
- Filtrer cette dernière requête pour ne faire apparaître que les factures dont le code postal est composé uniquement de chiffres
- Retourner le montant total des commandes passées en 2012
- Retourner la liste des clients avec les colonnes suivantes
  - Id du client
  - Nom, Prénom du client format (DUPONT, Jean)
  - Le nombre de commande passées
  - Le total de commandes passées
- A partir de la requête précédente, retourner les memes informations en deux requêtes:
  - La première qui n'affiche que les clients ayant acheté pour plus de 40 euros
  - La deuxième qui ne tient compte que des factures inférieures à 10 euros