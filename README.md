# SFDMU Demo
Cette Demo est conçue pour partir d'une org de Demo, avec les comptes de tests pat défaut, alias SFDMU-Prod
L'org Cible est une Sandbox Dev (ou une scratch) nommée SFDMU-0

## Installation de SFDMU
```
sfdx plugins:install sfdmu
```

## Demo 1
Simple copie des contacts

```
sfdx sfdmu run -p demo1 -s SFDMU-Prod -u SFDMU-0
```

## Demo 2
Copie Compte, Contacts, Opportunités

Pour les opportunités ajouter préalablement le champ ExternalId__c à la source et à la target (si déjà créée), et l'initialiser sur la source
````
sfdx project deploy start -p force-app
``````
Nb : cette commande ajoutera également le champ au profil admin

On peur ensuite lancer l'import
```
sfdx sfdmu run -p demo2 -s SFDMU-Prod -u SFDMU-0
```

Noter pour les Contacts qu'il y a un update pour mettre à jour les liens hiéracchiques

## Demo 3
Anonymisation des numéros de téléphone des contacts
```
sfdx sfdmu run -p demo3 -s SFDMU-Prod -u SFDMU-0
```
## Demo 4
Transformation des adresses e-mail

Modification sur la sandbox : 
```
sfdx sfdmu run -p demo4 -s SFDMU-0 -u SFDMU-0
``````