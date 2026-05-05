# Projet ProxiVroum - Plateforme de Covoiturage

## Exercice 1 - Démarche

### 1. User Stories (Format INVEST)
Chaque story est accompagnée d'un critère d'acceptation.

*   **User Story 1 (Conducteur) :** En tant que conducteur, je veux publier un trajet en indiquant le départ, l'arrivée et le prix, afin de trouver des passagers pour partager mes frais.
    *   **Critère d'acceptation :** Le trajet doit apparaître immédiatement dans les résultats de recherche après validation du formulaire.
*   **User Story 2 (Passager) :** En tant que passager, je veux rechercher un trajet par ville et date, afin de réserver une place pour mon déplacement.
    *   **Critère d'acceptation :** Le système doit afficher une liste de trajets disponibles correspondant exactement aux filtres saisis.
*   **User Story 3 (Comptabilité) :** En tant que service comptabilité, je veux exporter les transactions mensuelles au format CSV, afin d'intégrer les données dans notre logiciel de gestion.
    *   **Critère d'acceptation :** Le fichier généré doit contenir l'ID de la transaction, le montant, la date et le statut du paiement.

### 2. 3 Critères de Qualité Mesurables

*   **Disponibilité (Availability) :** Le système doit maintenir un taux de disponibilité de **99,5 %** sur une base mensuelle.
*   **Performance (Temps de réponse) :** En période de pic (vendredi et dimanche soir), le temps de réponse pour la recherche d'un trajet ne doit pas dépasser **2 secondes** pour 95 % des requêtes.
*   **Sécurité (Conformité) :** 100 % des données de paiement doivent être traitées via une passerelle certifiée **PCI-DSS**, sans stockage des numéros de carte sur nos serveurs.

### 3. 1 ADR (Architecture Decision Record)
L'ADR justifie un choix technique structurant pour le projet.

**Titre : Choix d'une base de données relationnelle (PostgreSQL)**
*   **Statut :** Accepté.
*   **Contexte :** ProxiVroum gère des transactions financières et des réservations qui nécessitent une forte cohérence des données.
*   **Décision :** Utiliser **PostgreSQL** comme base de données principale.
*   **Conséquences :**
    *   Garantie des propriétés **ACID** pour les paiements et réservations.
    *   Facilité de mise en conformité **RGPD** grâce aux outils de gestion des accès et de chiffrement.
    *   Capacité à gérer les montées de charge (via le read-scaling) pour les pics du weekend.
