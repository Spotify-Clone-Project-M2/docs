# Partie 1 : API Backend

### Technologies obligatoires

- **Runtime** : Node.js
- **Framework** : Express.js ou NestJS
- **Base de données** : MongoDB ou PostgreSQL
- **Cache** : Redis
- **CDN** : CloudFront ou CloudFlare
- **Storage** : S3 ou équivalent
- **Tests** : Jest
- **Documentation** : Swagger/OpenAPI

### Configuration du projet

- ✅ ESLint + Prettier (configuration stricte)
- ✅ Husky pour les pre-commit hooks
- ✅ Dockerfile et docker-compose.yml (Pour ceux qui souhaitent deployer via docker)
- ✅ Configuration du CI/CD (GitHub Actions ou GitLab CI ou solution de votre choix)
- ✅ Logs structurés (Winston ou Pino)
- ✅ Configuration via variables d'environnement (dotenv)

# LE NON RESPECT D’UNE DES EXIGENCES ENTRAINERA L’ATTRIBUTION D’UNE NOTE ÉLIMINATOIRE

### Fonctionnalités requises

### 1. Gestion des médias

- Conversion audio vers formats optimisés (.m4a, .wav)
- Traitement des images en plusieurs formats/tailles
    - Formats : WebP, JPEG, AVIF
    - Tailles : thumbnail, medium, large
    - Compression intelligente

### 2. API RESTful

<aside>
💡

Vous créerez vos schémas en vous basant sur les instructions demandées dans le projet.

</aside>

- CRUD complet pour :
    - Artistes
    - Albums
    - Pistes audio
    - Playlists
- Relations entre entités
- Pagination
- Filtrage
    - Filtrage par artiste : permettre aux utilisateurs de filtrer les albums ou les pistes audio par artiste spécifique
    - Filtrage par album : permettre de filtrer les pistes audio par album
    - Filtrage par genre musical : ajouter un attribut de genre aux artistes, albums ou pistes et permettre le filtrage basé sur ce critère
    - Filtrage par année de sortie : pour les albums ou les pistes audio
    - Filtrage par durée : pour les pistes audio, permettre de filtrer par plage de durée (ex : courtes, moyennes, longues)
    - Filtrage par popularité : basé sur le nombre d'écoutes ou une note moyenne
    - Filtrage par playlist : permettre aux utilisateurs de filtrer les pistes audio présentes dans une playlist spécifique
- Tri
    - Tri des pistes audio par durée (croissant ou décroissant)
    - Tri des albums par date de sortie
    - Tri des artistes par ordre alphabétique
    - Tri des playlists par nombre de pistes
    - Tri des pistes audio par popularité (basé sur le nombre d'écoutes)
    - Tri des albums par nombre de pistes
    - Tri des pistes audio par ordre alphabétique du titre
- **Recherche par mots-clés multiples** : Permettre aux utilisateurs de combiner plusieurs termes de recherche (artiste, titre, album, genre) pour affiner leurs résultats.
- **Recherche phonétique** : Implémenter un algorithme de recherche phonétique pour trouver des résultats même si l'orthographe n'est pas exacte, particulièrement utile pour les noms d'artistes ou les titres étrangers.
    <aside>
    💡
    
    Vous utiliserez l’algorithme Metaphone et la distance de Levenshtein pour faire la Recherche phonétique | devra fonctionner pour la recherche des artistes anglais
    
    </aside>
    
- **Auto-complétion intelligente** : Proposer des suggestions de recherche basées sur l'historique de l'utilisateur et les tendances populaires.
- **Recherche par similarité** : Permettre aux utilisateurs de trouver des morceaux similaires à une chanson donnée, basée sur des caractéristiques musicales comme le tempo, le genre, ou l'ambiance.
- **Recherche par paroles** : Intégrer une fonction de recherche dans les paroles des chansons.

### 3. Sécurité

- Authentication JWT
- Rate limiting
- Validation des données entrantes

<aside>
💡

Vous utiliserez une bibliothèque comme Joi pour effectuer la validation. Chaque endpoint sans validation de données entraînera une pénalité de points. 

</aside>

- Protection CSRF
    
    [**CSRF**](https://www.notion.so/CSRF-144858a1a0c38163b726e89aa25bdb4b?pvs=21)
    
- Headers de sécurité (helmet)
    
    [A quoi servent les headers de securité](https://www.notion.so/A-quoi-servent-les-headers-de-securit-144858a1a0c3819289d1f8dee9590a33?pvs=21)
    
- Gestion des permissions RBAC
    
    [Exemple RBAC](https://www.notion.so/Exemple-RBAC-144858a1a0c381fbbf11e21381906497?pvs=21)
    

### 4. Performance

- Cache Redis multi-niveaux
    - Cache de requêtes
    - Cache de fichiers
    - Cache de sessions
- Optimisation des requêtes DB
- Monitoring des performances
    - Temps de réponse des requêtes API
    - Utilisation des ressources serveur (CPU, mémoire, disque)
    - Temps d'exécution des requêtes de base de données
    - Taux de succès/échec des requêtes
    - Latence du cache Redis
    - Temps de traitement des médias (conversion audio, traitement d'images)
    - Utilisation de la bande passante
- Gestion des timeouts
    - Implémentez des timeouts pour les requêtes API afin d'éviter les attentes infinies
    - Configurez des timeouts pour les connexions à la base de données
    - Mettez en place des timeouts pour les opérations de traitement des médias
    - Assurez-vous de gérer correctement les erreurs de timeout et de fournir des réponses appropriées à l'utilisateur
    - Utilisez des retry mechanisms pour les opérations qui peuvent échouer temporairement

### 5. Scripts utilitaires

- Seeding de la base de données :
    - Créez un script qui parcourt les fichiers audio préparés
    - Extrayez les métadonnées existantes de chaque fichier audio (titre, artiste, durée, etc.)
    - Pour les champs manquants, utilisez Faker.js pour générer des données réalistes
    - Insérez ces informations dans la base de données, en créant les relations nécessaires
    - Assurez-vous de gérer les doublons potentiels (par exemple, vérifiez si l'artiste existe déjà)
    - Implémentez un système de logging pour suivre le processus et identifier les éventuelles erreurs
    - le script devra créer
        - Artiste
        - Album
        - Audios
    
    <aside>
    💡
    
    Le script devra gérer les relations entre artiste, album et audios, en s'assurant que chaque piste audio est correctement associée à son album et à son artiste. Il faudra également tenir compte des cas particuliers comme les compilations ou les albums avec plusieurs artistes. 
    
    </aside>
    
- Backup automatisé :
    - Créez un script pour sauvegarder automatiquement la base de données et les fichiers média
    - Utilisez des outils comme pg_dump pour PostgreSQL ou mongodump pour MongoDB
    - Implémentez une rotation des sauvegardes (garder les 7 derniers jours, puis une par semaine pour le mois précédent)
    - Stockez les sauvegardes sur un système de stockage distant (comme S3)
    - Ajoutez un système de notification en cas d'échec de la sauvegarde
        - ntfy.sh
    - Testez régulièrement la restauration des sauvegardes pour s'assurer de leur intégrité
- Nettoyage des fichiers temporaires

### Tests requis

- Tests unitaires (Quelques test)