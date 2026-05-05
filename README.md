# Projet ProxiVroum

## Exercice 1 - Démarche

### 1. User Stories (INVEST)
* **US 1 (Conducteur) :** En tant que conducteur, je veux publier un trajet pour partager mes frais.
    * *Critère d'acceptation :* Le trajet s'affiche dès la validation.
* **US 2 (Passager) :** En tant que passager, je veux rechercher un trajet pour réserver une place.
    * *Critère d'acceptation :* Les résultats correspondent aux villes choisies.
* **US 3 (Compta) :** En tant que comptable, je veux exporter les données en CSV.
    * *Critère d'acceptation :* Le fichier contient les montants et dates.

### 2. Qualité et Contraintes
* **Disponibilité :** 99,5 % (comme demandé dans le document 1000007498.jpg).
* **Performance :** Temps de réponse < 2 secondes pendant les pics.
* **Sécurité :** Données conformes au RGPD et paiements PCI-DSS.

### 3. ADR (Choix technique)
* **Choix :** PostgreSQL (Base de données).
* **Raison :** Pour sécuriser les transactions financières et la cohérence des données.
