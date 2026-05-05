# Projet ProxiVroum - Plateforme de Covoiturage

## 📝 Exercice 1 - Démarche

### 1. User Stories (Format INVEST)
Chaque story est accompagnée d'un critère d'acceptation.

*   **User Story 1 (Conducteur) :** En tant que conducteur, je veux publier un trajet en indiquant le départ, l'arrivée et le prix, afin de trouver des passagers pour partager mes frais[cite: 1, 2].
    *   **Critère d'acceptation :** Le trajet doit apparaître immédiatement dans les résultats de recherche après validation du formulaire[cite: 1, 2].
*   **User Story 2 (Passager) :** En tant que passager, je veux rechercher un trajet par ville et date, afin de réserver une place pour mon déplacement[cite: 1, 2].
    *   **Critère d'acceptation :** Le système doit afficher une liste de trajets disponibles correspondant exactement aux filtres saisis[cite: 1, 2].
*   **User Story 3 (Comptabilité) :** En tant que service comptabilité, je veux exporter les transactions mensuelles au format CSV, afin d'intégrer les données dans notre logiciel de gestion[cite: 1, 2].
    *   **Critère d'acceptation :** Le fichier généré doit contenir l'ID de la transaction, le montant, la date et le statut du paiement[cite: 1, 2].

### 2. 3 Critères de Qualité Mesurables
Ces critères répondent directement aux contraintes de haute disponibilité et de performance mentionnées dans l'énoncé[cite: 1, 2].

*   **Disponibilité (Availability) :** Le système doit maintenir un taux de disponibilité de **99,5 %** sur une base mensuelle (hors fenêtres de maintenance annoncées)[cite: 1, 2].
*   **Performance (Temps de réponse) :** En période de pic (vendredi et dimanche soir), le temps de réponse pour la recherche d'un trajet ne doit pas dépasser **2 secondes** pour 95 % des requêtes[cite: 1, 2].
*   **Sécurité (Conformité) :** 100 % des données de paiement doivent être traitées via une passerelle certifiée **PCI-DSS**, sans stockage des numéros de carte sur nos serveurs[cite: 1, 2].

### 3. 1 ADR (Architecture Decision Record)
L'ADR justifie un choix technique structurant pour le projet[cite: 1, 2].

**Titre : Choix d'une base de données relationnelle (PostgreSQL)**
*   **Statut :** Accepté[cite: 1, 2].
*   **Contexte :** ProxiVroum gère des transactions financières et des réservations qui nécessitent une forte cohérence des données[cite: 1, 2].
*   **Décision :** Utiliser **PostgreSQL** comme base de données principale[cite: 1, 2].
*   **Conséquences :**
    *   Garantie des propriétés **ACID** pour les paiements et réservations[cite: 1, 2].
    *   Facilité de mise en conformité **RGPD** grâce aux outils de gestion des accès et de chiffrement[cite: 1, 2].
    *   Capacité à gérer les montées de charge (via le read-scaling) pour les pics du weekend[cite: 1, 2].
