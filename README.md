# Kubernetes avec Minikube – Orchestration, disponibilité et sécurité des conteneurs

Un projet pratique visant à démontrer comment **Kubernetes** orchestre des applications conteneurisées à l'aide de **Minikube** dans un environnement de développement local.

## À propos du projet

Ce projet consiste à explorer Kubernetes à travers le déploiement et la gestion d'une petite application web développée avec **Flask** et **Redis**.

L'objectif est de comprendre les principes fondamentaux de l'orchestration des conteneurs et de démontrer comment Kubernetes facilite le déploiement, la disponibilité, la gestion des ressources et la sécurisation des applications.

Le projet est réalisé dans un environnement de laboratoire local utilisant Minikube.

## Objectifs du projet

- Comprendre l'architecture de Kubernetes et ses principaux composants.
- Installer et configurer un cluster Kubernetes local avec Minikube.
- Conteneuriser une application Flask et un service Redis.
- Déployer et gérer les composants de l'application avec Kubernetes.
- Démontrer la disponibilité de l'application grâce à la mise à l'échelle et à l'auto-réparation.
- Appliquer les bonnes pratiques de sécurité de base de Kubernetes.
- Documenter le processus de déploiement afin de permettre sa reproduction.

## Architecture de l'application

L'application de démonstration repose sur deux composants principaux :

- **Flask :** Gère l'application web et les requêtes des utilisateurs.
- **Redis :** Stocke et gère les données de l'application.

### Vue d'ensemble de l'architecture

```text
             Utilisateur
                  |
                  v
          Application Flask
                  |
                  v
                Redis
          (Service interne)
```

Kubernetes assure la gestion du déploiement et de la communication entre ces différents composants.

## Technologies utilisées

| Technologie | Rôle |
|---|---|
| Kubernetes | Orchestration des conteneurs |
| Minikube | Création d'un cluster Kubernetes local |
| Docker | Conteneurisation |
| kubectl | Gestion du cluster Kubernetes en ligne de commande |
| Python / Flask | Développement de l'application web |
| Redis | Stockage de données en mémoire |
| YAML | Configuration des ressources Kubernetes |
| Git / GitHub | Gestion des versions et collaboration |

## Fonctionnalités Kubernetes étudiées

Le projet vise à démontrer les fonctionnalités suivantes :

### 1. Déploiement de l'application

Déployer Flask et Redis à l'aide des ressources Kubernetes : Deployments, Pods et Services.

### 2. Auto-réparation (Self-Healing)

Supprimer un Pod en cours d'exécution et observer comment Kubernetes en crée automatiquement un nouveau pour le remplacer.

### 3. Mise à l'échelle (Scaling)

Augmenter le nombre de réplicas de Flask afin de démontrer la mise à l'échelle horizontale de l'application.

### 4. Mises à jour progressives et retours en arrière

Mettre à jour progressivement l'application et démontrer comment revenir à une version précédente en cas de problème.

### 5. Sécurité

Appliquer des mesures de sécurité de base, notamment :

- Utilisation des Kubernetes Secrets pour les configurations sensibles.
- Exécution des conteneurs avec un utilisateur non privilégié (non-root).
- Définition de limites de ressources CPU et mémoire.
- Utilisation des Network Policies pour contrôler les communications réseau.
- Gestion des autorisations avec le contrôle d'accès basé sur les rôles (RBAC).

## Structure du projet

```text
Kubernetes-minikube/
│
├── app/
│   ├── app.py
│   ├── requirements.txt
│   └── Dockerfile
│
├── kubernetes/
│   ├── flask-deployment.yaml
│   ├── flask-service.yaml
│   ├── redis-deployment.yaml
│   ├── redis-service.yaml
│   ├── redis-secret.yaml
│   └── network-policy.yaml
│
├── tests/
│   └── test-cases.md
│
├── docs/
│   └── architecture.md
│
└── README.md
```

*La structure du dépôt pourra évoluer au fur et à mesure de l'avancement du projet.*

## Prérequis

Avant de commencer, assurez-vous d'avoir installé les outils suivants :

- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- [Git](https://git-scm.com/downloads)

## Installation et démarrage

### 1. Démarrer Minikube

```bash
minikube start
```

### 2. Vérifier l'état du cluster

```bash
kubectl get nodes
```

### 3. Cloner le dépôt GitHub

```bash
git clone https://github.com/Alfred-bit-co/Kubernetes-minikube.git
```

### 4. Accéder au dossier du projet

```bash
cd Kubernetes-minikube
```

### 5. Déployer l'application

```bash
kubectl apply -f kubernetes/
```

### 6. Vérifier les ressources déployées

```bash
kubectl get pods
kubectl get services
kubectl get deployments
```

*Remarque : Les commandes de déploiement seront pleinement utilisables une fois que les fichiers de l'application et les manifestes Kubernetes auront été créés.*

## Tests et évaluation

Le projet prévoit des tests destinés à évaluer :

- Le bon fonctionnement du déploiement de l'application.
- La communication entre Flask et Redis.
- La récupération automatique des Pods après leur suppression.
- La mise à l'échelle de l'application.
- Les mises à jour progressives et les retours en arrière.
- L'application des configurations de sécurité.

Les résultats des tests et les preuves correspondantes seront documentés dans les dossiers `tests/` et `docs/`.

## Périmètre du projet

Ce projet se concentre sur un **cluster Kubernetes local à un seul nœud**, exécuté à l'aide de Minikube.

Il est destiné à des fins pédagogiques et expérimentales. Il ne vise pas à fournir une infrastructure de production ni une architecture de haute disponibilité multi-nœuds.

## Membres de l'équipe

- **ATTOH Séverine**
- **DOSSOH Guillaume**
- **AYITOU Alfred**
- **MABIALA Lys**

**Encadrant :** Monsieur TETE Kodjovi

## Contexte académique

Ce projet s'inscrit dans le cadre d'une formation en génie logiciel. Il porte sur l'orchestration des conteneurs, la disponibilité des applications et leur sécurisation.

---

**État du projet :** En cours de développement

**Environnement :** Cluster Kubernetes local – Minikube

**Dépôt :** GitHub
