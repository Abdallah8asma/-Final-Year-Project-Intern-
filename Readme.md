# 🚀 Projet de Fin d'Études – Système GPRO Consulting ERP

## 📋 Description du Projet

Le projet **GPro** a été réalisé dans le cadre de mon stage de fin d'études. Il s'agit d'une solution complète pour la gestion des modules logistiques, communs et front-end, destinée à automatiser et sécuriser les processus métiers au sein d'une entreprise.

L'objectif principal était de concevoir un système modulaire, scalable et sécurisé, facile à déployer et à maintenir grâce aux pratiques DevSecOps.

---

## 🏗️ Architecture de la Solution

### Diagramme d'Architecture

```
                +------------------+
                |  Frontend Angular |
                +--------+---------+
                         |
                         v
         +-------------------------------+
         |        API Gateway REST        |
         +-------------------------------+
          |           |           |
          v           v           v
 +----------------+ +----------------+ +----------------+
 | Service Commun | | Service Socle  | | Service Logist.|
 |  Spring Boot   | |  Spring Boot   | |  Spring Boot   |
 +----------------+ +----------------+ +----------------+
          |                   |           |
          +---------+---------+-----------+
                    |
                    v
             +----------------+
             |  PostgreSQL    |
             |   Database     |
             +----------------+
```

### Composants Architecturaux

| Couche | Composant | Technologie | Description |
|--------|-----------|-------------|-------------|
| **Présentation** | Frontend Web | Angular 15 | Interface utilisateur responsive |
| **API Gateway** | Gateway | Spring Cloud Gateway | Routage et agrégation des APIs |
| **Services Métier** | Microservices | Spring Boot 3.x | Services modulaires indépendants |
| **Données** | Base de données | PostgreSQL 14 | Stockage relationnel des données |
| **Infrastructure** | Cloud | AWS EC2 | Hébergement et déploiement |

---

## 🚀 Déploiement sur AWS EC2

### Infrastructure Cloud

#### Configuration des Instances EC2

| Service | Instance Type | Ports Ouverts | Description |
|---------|---------------|---------------|-------------|
| **Application** | t3.medium | 80, 443, 8080-8082 | Héberge tous les services applicatifs |
| **Base de données** | t3.small | 5432 | Instance dédiée PostgreSQL |

### Pipeline CI/CD Jenkins

#### Étapes du Pipeline

1. **Build** - Compilation des projets Maven
2. **Test** - Exécution des tests unitaires et d'intégration
3. **Analyse Qualité** - Scan SonarQube
4. **Build Docker** - Création des images Docker
5. **Scan Sécurité** - Analyse Trivy des images
6. **Déploiement** - Déploiement automatique sur EC2

### Conteneurisation avec Docker

#### Architecture des Conteneurs

- **Frontend** : Conteneur Nginx servant l'application Angular
- **Backend Services** : Conteneurs Spring Boot indépendants
- **Base de données** : Conteneur PostgreSQL avec volume persistant
- **Réseau** : Docker network pour l'isolation et communication

---

## 🛠️ Outils et Technologies Utilisés

### Développement
- **Java 17** - Langage backend principal
- **Spring Boot 3.0** - Framework d'application
- **Angular 15** - Framework frontend
- **TypeScript 4.5** - Langage frontend

### Base de Données
- **PostgreSQL 14** - Base de données relationnelle

### DevOps & Cloud
- **Docker 20.10** - Conteneurisation
- **AWS EC2** - Infrastructure cloud
- **Jenkins 2.375** - Automatisation CI/CD

### Qualité & Sécurité
- **SonarQube 9.7** - Analyse qualité code
- **Trivy 0.32** - Scan sécurité containers
- **Nexus 3.41** - Gestion artefacts

### Contrôle de Version
- **Git 2.35** - Versioning code
- **GitHub** - Hébergement repository

---

## 📁 Structure des Modules

### Backend Services
- **Module Socle** : Services de base et configuration centrale
- **Module Commun** : Fonctionnalités partagées entre les modules
- **Module Logistique** : Gestion de la chaîne logistique
- **Module Design** : Services de présentation et interface
- **Module Atelier** : Gestion des ateliers de production

### Frontend
- **Application Angular** : Interface utilisateur unifiée
- **Components Partagés** : Bibliothèque de composants réutilisables
- **Services API** : Communication avec les microservices backend

---

## 🔧 Processus de Déploiement

### Préparation de l'Environnement

1. **Configuration AWS EC2**
   - Lancement d'instance Amazon Linux 2
   - Configuration des Security Groups
   - Attribution d'IP Élastique

2. **Installation des Dépendances**
   - Docker et Docker Compose
   - Java Runtime Environment
   - Configuration du réseau

### Déploiement Automatisé

1. **Intégration Continue**
   - Déclenchement sur push Git
   - Build et tests automatiques
   - Génération des artefacts

2. **Livraison Continue**
   - Construction des images Docker
   - Scan de sécurité des images
   - Déploiement sur EC2 via SSH

3. **Post-Déploiement**
   - Tests de smoke
   - Vérification de la santé des services
   - Notification du statut

---

## ✅ Fonctionnalités Principales

### Modules Métier
- **Gestion Logistique** : Suivi des stocks, commandes et livraisons
- **Services Communs** : Authentification, logging, configuration
- **Module Socle** : Infrastructure de base et API gateway

### Sécurité
- Authentification JWT et gestion des rôles
- Scan continu des vulnérabilités
- Chiffrement des données sensibles
- Conformité aux bonnes pratiques OWASP

### Qualité et Maintenance
- Monitoring des performances
- Logs centralisés et analyse
- Métriques de santé des services
- Sauvegardes automatiques

---

## 🌟 Points Forts de l'Architecture

### Modularité
- Services indépendants et déployables séparément
- APIs bien définies et versionnées
- Découplage des responsabilités

### Scalabilité
- Architecture horizontale sur EC2
- Base de données optimisée pour les charges importantes
- Load balancing intégré

### Maintenabilité
- Code documenté et tests automatisés
- Pipeline CI/CD robuste
- Monitoring et alerting proactifs

---

## 👨‍💻 Auteur

**Asma Abdallah**

- DevSecOps & Cloud Engineer
- Professeur en informatique

---

## 📄 Licence

Ce projet est développé dans le cadre d'un projet de fin d'études. Tous droits réservés.

---

**"L'excellence n'est pas un acte, mais une habitude."** - Aristote
