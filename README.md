# 🛒 Projet SQL : Base de Données Commerciale

Bienvenue dans ce dépôt ! Cette section du projet est dédiée à l'interrogation et à l'analyse d'une base de données commerciale typique. 

## 🚀 Contexte et Mise en place

L'environnement de données de ce projet est initialisé à l'aide du script fourni :
- `commercial.sql` : Ce script s'occupe de la création des tables (Employés, Clients, Fournisseurs, Produits, Commandes, etc.) et de l'insertion du jeu de données nécessaire.

**Pour démarrer :**
Exécutez en premier le script `commercial.sql` dans votre Système de Gestion de Base de Données (SGBD) afin de préparer l'environnement.

---

## 📋 Liste des Requêtes et Exercices Implémentés

Ce répertoire regroupe les scripts répondant aux problématiques d'extraction de données (DQL) suivantes :

1. **Analyse des employés à haut salaire**
   - *Objectif* : Lister, par ordre décroissant d'ancienneté, les employés masculins ayant un salaire net (salaire + commission) supérieur ou égal à 8000.
   - *Données affichées* : Numéro d'employé, Prénom et Nom, Âge, Ancienneté.

2. **Recherche de produits multicritères**
   - *Objectif* : Trouver les produits conditionnés en bouteille(s), dont le 3ème caractère du nom est 't' ou 'T', provenant des fournisseurs 1, 2 ou 3, avec un prix unitaire entre 70 et 200, et ayant des unités en commande.
   - *Données affichées* : Numéro du produit, Nom, Numéro du fournisseur, Unités commandées, Prix unitaire.

3. **Clients partageant la région d'un fournisseur (Sous-requêtes)**
   - *Objectif* : Afficher tous les clients résidant dans la même région que le "fournisseur 1" (même pays, même ville, et 3 derniers chiffres du code postal identiques) en utilisant une seule sous-requête.
   - *Données affichées* : Toutes les colonnes de la table client.

4. **Calcul dynamique de taux de remise (Conditions `CASE`)**
   - *Objectif* : Mettre à jour et analyser les remises pour les commandes N° 10998 à 11003. Le nouveau taux est défini selon le montant total (prix unitaire * quantité) :
     - `0%` si le montant est entre 0 et 2000.
     - `5%` s'il est entre 2001 et 10000.
     - `10%` s'il est entre 10001 et 40000.
     - `15%` s'il est entre 40001 et 80000.
     - `20%` pour tout montant supérieur.
   - Ajout d'une note dynamique demandant l'application de l'ancien taux pour les commandes < 11000, et le nouveau pour les autres.

5. **Filtrage par Catégorie de Produits**
   - *Objectif* : Lister tous les fournisseurs spécialisés dans les produits de type "boissons".
   - *Données affichées* : Numéro du fournisseur, Société, Adresse, Numéro de téléphone.

6. **Analyse des habitudes de consommation (Berlin)**
   - *Objectif* : Cibler les clients basés à Berlin ayant commandé un maximum de 1 produit de catégorie "dessert".
   - *Données affichées* : Code client.

7. **Suivi temporel des commandes (Avril 1998)**
   - *Objectif* : Afficher le montant total des commandes passées chaque lundi du mois d'avril 1998 par les clients français. (Gère également les clients n'ayant rien commandé via jointure externe).
   - *Données affichées* : Numéro client, Nom de la société, Numéro de téléphone, Montant total, Pays.

8. **Requête universelle (Division)**
   - *Objectif* : Trouver les clients très fidèles ayant commandé l'intégralité des produits du catalogue.
   - *Données affichées* : Code client, Nom de la société, Numéro de téléphone.

9. **Volume de commandes par client**
   - *Objectif* : Afficher le nombre total de commandes passées par chaque client basé en France.
   - *Données affichées* : Code client, Nombre de commandes.

10. **Comparaison inter-annuelle des ventes**
    - *Objectif* : Calculer et comparer le volume des commandes passées sur deux années distinctes (1996 et 1997).
    - *Données affichées* : Commandes en 1996, Commandes en 1997, Différence.
