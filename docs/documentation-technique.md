---
layout: default
title: Documentation technique
nav_order: 5
---

# Documentation technique

## 1. Vue d'ensemble du projet

E-CARE est une application mobile multiplateforme dédiée à l'organisation personnelle et au suivi nutritionnel. L'application vise à centraliser les besoins essentiels autour de l'alimentation, de l'organisation et du bien-être dans une interface intuitive et accessible.


## 2. Architecture technique

### 2.1 Stack technologique

| Technologie | Version | Rôle |
|-------------|---------|------|
| **Flutter** | Latest stable | Framework de développement multiplateforme (Android, iOS, Web, Desktop) |
| **Spoonacular API** | v1 | Génération de menus, informations nutritionnelles, base de recettes |
| **Firebase** | v9+ | Authentification Google, backend, configuration projet |

### 2.2 Architecture générale

```
┌─────────────────────────────────────────┐
│                FRONTEND                 │
│              (Flutter App)              │
├─────────────────────────────────────────┤
│              NAVIGATION                 │
│            (Flutter Router)             │
├─────────────────────────────────────────┤
│                BACKEND                  │
│             (Firebase)                  │
├─────────────────────────────────────────┤
│                  API                    │
│           (Spoonacular API)             │
└─────────────────────────────────────────┘
```

### 2.3 Type d'application
- **Client-side** : Application mobile s'exécutant directement sur l'appareil utilisateur
- **Multiplateforme** : Compatible , Android, Web 
- **Modulaire** : Architecture en modules indépendants pour faciliter le développement et la maintenance

## 3. Fonctionnalités techniques

### 3.1 Authentification
- **Provider** : Firebase Authentication
- **Méthode** : Connexion via compte Google
- **Sécurité** : Gestion des tokens et sessions via Firebase

### 3.2 Calcul nutritionnel
- **Algorithme** : Équation de Mifflin-St Jeor pour le métabolisme de base
- **Formule hommes** : BMR = 10 × poids(kg) + 6.25 × taille(cm) - 5 × âge(ans) + 5
- **Formule femmes** : BMR = 10 × poids(kg) + 6.25 × taille(cm) - 5 × âge(ans) - 161

### 3.3 Intégration API Spoonacular
- **Endpoints utilisés** :
  - `/recipes/complexSearch` : Recherche de recettes
  - `/recipes/{id}/information` : Détails nutritionnels
  - `/mealplanner/generate` : Génération de menus
  - `/recipes/{id}/analyzedInstructions` : Instructions de préparation

### 3.4 Base de données
- **Solution** : API externe (Spoonacular) pour éviter la gestion d'infrastructure
- **Données locales** : Cache Flutter pour les favoris et préférences utilisateur
- **Synchronisation** : Via Firebase pour la persistance des données utilisateur

## 4. Modules fonctionnels

###  Module Authentification
###  Module Calcul Calorique
###  Module Recettes


## 5. Interface utilisateur

- **Écrans principaux** :
  - Accueil/Dashboard
  - Recherche de recettes
  - Calcul calorique
  - Profil utilisateur
  - Favoris

## 6. Gestion de projet et développement

### 6.1 Méthodologie
- **Approche** : Méthode Agile adaptée
- **Outils** : Trello pour le suivi des tâches, GitHub pour le versioning
- **Branches** : Développement en branches parallèles pour la modularité

### 6.2 Workflow de développement
```
main (production)
├── develop (intégration)
│   ├── feature/auth
│   ├── feature/recipes
│   ├── feature/calculator
│   └── feature/ui
```

## 7. Tests et déploiement

### 7.1 Stratégie de tests
- **Tests unitaires** : Logique métier et calculs
- **Tests d'intégration** : API calls et authentification
- **Tests UI** : Parcours utilisateur critiques

### 7.2 Déploiement
- **Android** : Google Play Store
- **Web** : Firebase Hosting
- **CI/CD** : GitHub Actions pour l'automatisation

## 8. Sécurité et performances

### 8.1 Sécurité
- **Authentification** : OAuth 2.0 via Google
- **API Keys** : Stockage sécurisé via variables d'environnement
- **Données utilisateur** : Chiffrement via Firebase



