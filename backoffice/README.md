# Partie 2 : Backoffice

## Technologies obligatoires

- **Framework** : React, Next
- **State Management** : Redux Toolkit
- **Styling** : Styled Components

## Configuration requise

- ✅ ESLint + Prettier (configuration stricte)
- ✅ Husky pour les pre-commit hooks

# LE NON RESPECT D’UNE DES EXIGENCES ENTRAINERA L’ATTRIBUTION D’UNE NOTE ÉLIMINATOIRE

## Fonctionnalités requises

### 1. Dashboard avancé

### Statistiques en temps réel

- Métriques de performance système :
    - Temps de réponse des requêtes API
    - Utilisation des ressources serveur (CPU, mémoire, disque)
    - Latence du cache Redis
    - Utilisation de la bande passante
- Métriques métier :
    - Nombre de streams
    - Utilisateurs actifs
    - Espace stockage utilisé
    - Taux de succès/échec des requêtes
    - Temps de traitement des médias

### KPIs configurables

- Interface de configuration permettant de :
    - Sélectionner les KPIs à afficher
    - Réorganiser l'affichage (drag & drop)
    - Définir des seuils d'alerte personnalisés
        - ntfy.sh
    - Choisir le type de visualisation (graphique, compteur, jauge)
- Persistence des préférences utilisateur
- Système de notifications pour les seuils d'alerte
    - ntfy.sh

### 2. Gestion avancée des médias

### Upload et conversion

- Upload drag & drop multi-fichiers
- Support des formats :
    - Audio : conversion vers .m4a, .wav
    - Images : conversion vers WebP, JPEG, AVIF
- Génération automatique de plusieurs tailles d'images :
    - Thumbnail
    - Medium
    - Large
- Barre de progression détaillée :
    - Pourcentage d'upload
    - Statut de conversion
    - Estimation du temps restant

### Prévisualisation et contrôle qualité

- Prévisualisation audio avec waveform
- Prévisualisation des différents formats d'image
- Validation des métadonnées
- Système de reprise sur erreur

### 3. Gestion enrichie des catalogues

### Interface de gestion des artistes

- CRUD complet avec validation des données
- Gestion des métadonnées enrichies
- Support de la recherche phonétique pour les noms d'artistes
- Système de suggestion pour les artistes similaires

### Gestion des albums

- Interface intuitive de création/édition
- Réorganisation drag & drop des pistes
- Gestion avancée des métadonnées :
    - Informations de base (titre, date, genre)
    - Artistes collaborateurs
    - Crédits
    - Artwork en multiple formats
- Prévisualisation complète de l'album
- Système de validation avant publication

### 4. Recherche et filtrage avancés

### Interface de recherche

- Recherche instantanée multi-critères
- Support de la recherche phonétique
- Auto-complétion intelligente
- Historique des recherches

### Système de filtrage complet

- Filtres combinables :
    - Par artiste
    - Par album
    - Par genre musical
    - Par année de sortie
    - Par durée
    - Par popularité
    - Par playlist

### Options de tri avancées

- Tri multi-critères :
    - Durée
    - Date de sortie
    - Ordre alphabétique
    - Popularité
    - Nombre de pistes
    - Nombre d'écoutes

### 5. Optimisation des performances

### Optimisations techniques

- Code splitting par route et par fonctionnalité
- Lazy loading des composants lourds
- Mise en cache intelligente des requêtes
- Debouncing des recherches
- Throttling des actions utilisateur intensives
- Virtual scrolling pour les listes longues

### 6. Sécurité et contrôle d'accès

### Système RBAC intégré

- Interface d'administration des rôles

<aside>
💡

L'interface d'administration des rôles est un outil graphique permettant de gérer et configurer les différents rôles et leurs permissions dans un système de contrôle d'accès basé sur les rôles (RBAC). Elle permet aux administrateurs de créer, modifier et supprimer des rôles, ainsi que d'attribuer des permissions spécifiques à chaque rôle de manière centralisée.

c’est l’utilisateur Root qui définira les permissions.

</aside>

- Gestion fine des permissions

<aside>
💡

La gestion fine des permissions fait référence à un système de contrôle d'accès détaillé qui permet d'attribuer des droits spécifiques à différents utilisateurs ou groupes d'utilisateurs. Cela offre une granularité élevée dans la définition des autorisations, permettant une personnalisation précise des accès aux fonctionnalités ou aux données d'un système.

Voici quelques exemples concrets de gestion fine des permissions dans le contexte de notre projet spotify :

- Administrateur de contenu : Peut ajouter, modifier et supprimer des artistes, albums et pistes, mais n'a pas accès aux données utilisateur ou aux statistiques financières.
- Gestionnaire de catalogue : Peut uniquement modifier les métadonnées des artistes et des albums, sans pouvoir ajouter ou supprimer du contenu.
- Modérateur : Peut examiner et valider les nouveaux contenus soumis, mais ne peut pas modifier les contenus existants.
- Analyste : A accès en lecture seule aux statistiques d'écoute et aux rapports de performance, sans pouvoir modifier les données.

Cette granularité permet d'attribuer précisément les droits nécessaires à chaque rôle, renforçant ainsi la sécurité et l'efficacité du système.

</aside>

- Audit log des actions administrateurs

<aside>
💡

Un audit log des actions administrateurs est un enregistrement détaillé et chronologique de toutes les activités effectuées par les utilisateurs ayant des droits d'administration dans un système informatique. Il permet de suivre et de vérifier les actions importantes pour des raisons de sécurité et de conformité.

</aside>

### Sécurité renforcée

- Protection CSRF

<aside>
💡

La Protection CSRF (Cross-Site Request Forgery) est une mesure de sécurité visant à empêcher les attaques où un site malveillant exploite l'authentification d'un utilisateur sur un autre site pour effectuer des actions non autorisées. Elle implique généralement l'utilisation de jetons uniques pour valider les requêtes.

</aside>

- Validation des données côté client

<aside>
💡

La validation des données côté client est un processus de vérification des entrées utilisateur directement dans le navigateur avant leur envoi au serveur. Cette pratique améliore l'expérience utilisateur en fournissant un retour instantané et réduit la charge sur le serveur en filtrant les données invalides.

</aside>

- Gestion sécurisée des tokens

<aside>
💡

La gestion sécurisée des tokens fait référence aux pratiques et techniques utilisées pour manipuler, stocker et transmettre de manière sûre les jetons d'authentification dans une application. Cela inclut généralement le chiffrement, la rotation régulière des tokens, et leur stockage sécurisé pour prévenir les accès non autorisés et les attaques potentielles.

</aside>

- Mode hors ligne
- Thèmes Jour/Nuit
- Internationalisation (i18n) [seulement les données statique]
- Accessibilité WCAG AA

Vous devrez le jour de l’evaluation faire un audit lighthouse sur le site, le score devra etre supérieur à 85. 

## Points d'attention particuliers

- Validation stricte des données avant envoi au backend
- Gestion cohérente des erreurs
- Feedback utilisateur clair et informatif