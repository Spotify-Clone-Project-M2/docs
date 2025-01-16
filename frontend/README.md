# Projet Final - Application Spotify (Frontend)

## 📋 Vue d'ensemble

Ce projet vise à développer une application web moderne reproduisant les fonctionnalités principales de Spotify, en exploitant pleinement l'API backend existante.

## Technologies obligatoires

- [x] **Framework**: React / Next.js
- [ ] **State Management**: Redux Toolkit / Context
- [ ] **Styling**: Styled Components

## Configuration requise

- [x] ESLint + Prettier (configuration stricte)
- [x] Husky pour les pre-commit hooks
- [x] Configuration PWA complète
- [x] Support i18n

# LE NON RESPECT D'UNE DES EXIGENCES ENTRAINERA L'ATTRIBUTION D'UNE NOTE ÉLIMINATOIRE

## 1. Page d'accueil et Navigation

### 1.1 Interface principale

- [x] Affichage des dernières sorties avec défilement horizontal :
    - [x] Top 10 des derniers sons
    - [x] Top 10 des artistes populaires
    - [x] Top 10 des albums récents
- [ ] Implémentation du virtual scrolling pour les listes longues
- [x] Support du mode sombre/clair
- [ ] Adaptation responsive (mobile, desktop)

### 1.2 Lecteur Audio Avancé

- [ ] Fonctionnalités de base :
    - [ ] Lecture/Pause
    - [ ] Navigation temporelle
    - [ ] Contrôle du volume avec barre de progression
    - [ ] Mute/Unmute
    - [ ] Support du format .m4a et .wav (fournis par le backend)
- [ ] Modes de lecture :
    - [ ] Répétition de playlist
    - [ ] Répétition d'une chanson
    - [ ] Lecture aléatoire
- [ ] Interface fullscreen :
    - [ ] Affichage des artworks en format optimal
    - [ ] Métadonnées enrichies (artiste, album)
    - [ ] Visualisation de la waveform
    - [ ] Support des différents formats d'image (WebP, JPEG, AVIF)

## 2. Fonctionnalités Sociales et Collaboratives

### 2.1 Écoute Simultanée

- [ ] Système de salles virtuelles :
    - [ ] Génération d'URLs de partage
    - [ ] Interface de connexion à une salle
    - [ ] Synchronisation WebSocket avec le backend
    - [ ] Affichage des participants actifs
- [ ] Contrôles partagés :
    - [ ] Synchronisation de la lecture/pause
    - [ ] Synchronisation de la position de lecture

### 2.2 Playlists Dynamiques

- [ ] Playlist "Dernières écoutes" :
    - [ ] Affichage des 20 dernières musiques
    - [ ] Tri chronologique inverse
    - [ ] Mise à jour en temps réel
- [ ] Playlist "Les plus écoutées" :
    - [ ] Classement basé sur les statistiques d'écoute
    - [ ] Mise à jour automatique

## 3. Recherche et Navigation

### 3.1 Système de recherche avancé

- [ ] Recherche instantanée (mise à jour à chaque frappe)
    
    <aside>
    💡
    
    Pour une recherche instantanée efficace et performante, suivez ces bonnes pratiques :
    
    - [ ] Utilisez le debouncing pour limiter les appels API
    - [ ] Implémentez la mise en cache des résultats récents
    - [ ] Optimisez les requêtes côté serveur pour des réponses rapides
    - [ ] Affichez un indicateur de chargement pour une meilleure expérience utilisateur
    - [ ] Limitez le nombre de résultats affichés initialement
    - [ ] Utilisez l'autocomplétion pour guider l'utilisateur
    - [ ] Gérez correctement les erreurs et les cas de résultats vides
    </aside>
    
- [ ] Implémentation des fonctionnalités backend :
    - [ ] Recherche phonétique pour les artistes
    - [ ] Recherche par mots-clés multiples
    - [ ] Auto-complétion intelligente
    - [ ] Support de la recherche par similarité

### 3.2 Filtres et Tri

- [ ] Filtres avancés :
    - [ ] Par artiste
    - [ ] Par album
    - [ ] Par genre musical
    - [ ] Par année de sortie
    - [ ] Par durée
    - [ ] Par popularité
- [ ] Options de tri :
    - [ ] Durée des pistes
    - [ ] Date de sortie
    - [ ] Ordre alphabétique
    - [ ] Popularité
    - [ ] Nombre d'écoutes

## 4. Performance et Optimisation

### 4.1 Optimisations techniques

- [ ] Implémentation du cache côté client

<aside>
💡

L'implémentation du cache côté client est une technique d'optimisation qui consiste à stocker temporairement des données sur l'appareil de l'utilisateur. Cela permet d'améliorer les performances en réduisant les requêtes au serveur et en accélérant le chargement des données fréquemment utilisées.

</aside>

- [ ] Lazy loading des composants
- [ ] Optimisation des images :
    - [ ] Utilisation des formats adaptés (WebP, AVIF)
    - [ ] Chargement progressif
    
    <aside>
    💡
    
    Le chargement progressif est une technique d'optimisation qui consiste à charger les images par étapes, en commençant par une version basse résolution qui s'améliore progressivement jusqu'à la qualité finale. Cela permet d'afficher rapidement un aperçu de l'image tout en améliorant l'expérience utilisateur, notamment sur les connexions lentes.
    
    </aside>
    
    - [ ] Tailles responsive

### 4.2 Mode Hors-ligne

- [ ] Service Worker pour le cache (PWA)

<aside>
💡

Un Service Worker est un script qui s'exécute en arrière-plan dans le navigateur, permettant d'implémenter des fonctionnalités avancées pour les applications web, notamment la gestion du cache pour le mode hors-ligne. Il intercepte les requêtes réseau et permet de contrôler la mise en cache des ressources pour améliorer les performances et l'expérience utilisateur.

</aside>

- [ ] Synchronisation différée

<aside>
💡

La synchronisation différée est une technique permettant à une application web de fonctionner hors ligne en stockant les modifications localement, puis en les synchronisant avec le serveur une fois la connexion rétablie. Cela améliore l'expérience utilisateur en permettant une utilisation continue, même sans connexion internet.

</aside>

- [ ] Indicateur de connexion

<aside>
💡

Un indicateur de connexion est un élément d'interface utilisateur qui affiche l'état actuel de la connexion internet de l'utilisateur. Il permet aux utilisateurs de savoir s'ils sont en ligne ou hors ligne, ce qui est particulièrement utile dans le contexte d'une application web avec des fonctionnalités hors ligne.

</aside>

## 5. Accessibilité et Internationalisation

### 5.1 Accessibilité WCAG AA

- [ ] Navigation au clavier
- [ ] Support des lecteurs d'écran
- [ ] Contraste et lisibilité
- [ ] Messages d'erreur vocaux

### 5.2 Internationalisation

- [ ] Support multilingue
    - [ ] Francais
    - [ ] Anglais
    - [ ] Arabe littéraire
- [ ] RTL/LTR selon la langue
- [ ] Formats de date localisés
- [ ] Messages d'erreur traduits

## 6. Sécurité et Gestion des Erreurs

### 6.1 Sécurité

- [ ] Protection CSRF (intégration avec le backend)
- [ ] Validation des données côté client
- [ ] Gestion sécurisée des tokens

### 6.2 Gestion des erreurs

- [ ] Messages d'erreur contextuels
    - [ ] Toast affichage
- [ ] Fallbacks appropriés
- [ ] Retry automatique sur échec
- [ ] Feedback utilisateur clair

## Points d'attention particuliers

- [ ] Interface intuitive et réactive
- [ ] Cohérence visuelle globale
- [ ] Gestion appropriée des états de chargement
- [ ] Optimisation des performances