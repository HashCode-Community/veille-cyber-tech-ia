# 📡🤖 Moteur de Veille Cyber & IA — Roadmap d'équipe

> 🎓 Projet étudiant en cybersécurité — réalisé en équipe.

## 🎯 Objectif

Construire un moteur de veille technologique et informationnelle qui
agrège automatiquement du contenu (actualités, articles, publications)
sur trois thématiques : **cybersécurité**, **informatique** et **IA
agentique**, le stocke, le classe, et le rend consultable/filtrable.

## 👥 Public cible

- 🔭 L'auteur lui-même, pour suivre l'actualité sans consulter des
  dizaines de sites manuellement.
- 🌍 Toute personne (étudiants, professionnels) souhaitant une veille
  centralisée sur ces sujets.

## 🧰 Prérequis

- 🐍 Notions de base en programmation backend (au choix : Python, Node.js,
  etc.).
- 📡 Notions de base sur les flux RSS/Atom et les API REST.
- 🗄️ Un système de base de données (SQLite suffit pour démarrer).

## 🤝 Équipe & organisation

- 🧭 **Coordinateur  :** Malick Ramzy SOPODOU.
- 🧑‍🤝‍🧑 **Coéquipier dédié à ce projet :** Jose.
- 🎓 **Mentor :** Mr Eurin — voir "📊 Suivi & compte-rendu au mentor"
  ci-dessous.

### 🧩 Répartition des rôles proposée (à ajuster ensemble)

| Rôle | Responsabilités principales |
|---|---|
| **🔄 Collecte & automatisation** | Sources RSS, script de collecte, dédoublonnage, planification périodique, gestion des erreurs (Phases 3, 4). |
| **📊 Exposition & restitution** | Schéma de données, endpoints de consultation/filtrage, interface éventuelle, enrichissement bonus (Phases 5, 6, 7). |

La Phase 1 (cadrage : stack, sources, format de restitution) se fait
ensemble, en amont du reste.

## 🛠️ Choix techniques (indicatif, adaptable)

| Besoin | Option recommandée | Alternatives |
|---|---|---|
| Backend / API | Python + FastAPI | Node.js + Express, Django |
| Base de données | SQLite (démarrage) → PostgreSQL (production) | MongoDB si contenu peu structuré |
| Collecte | Flux RSS/Atom (`feedparser` en Python) | Scraping HTML pour sites sans RSS |
| Planification | APScheduler / cron | Tâche planifiée système |
| Restitution | API REST + dashboard web simple | Export CSV/JSON, newsletter |

## ✨ Fonctionnalités attendues

### 🚀 MVP (indispensable)

- [ ] Liste de sources RSS définie pour chacune des 3 catégories.
- [ ] Script de collecte qui récupère les nouveaux articles des sources.
- [ ] Stockage en base avec dédoublonnage (un même article ne doit pas
      être inséré deux fois).
- [ ] Chaque article stocké contient : titre, lien, résumé, source,
      catégorie, date de publication.
- [ ] Endpoint/vue permettant de lister les articles filtrés par
      catégorie, source ou mot-clé.
- [ ] Collecte automatisée à intervalle régulier (pas seulement manuelle).

### 🎁 Bonus (si le temps le permet)

- [ ] Résumé automatique des articles via un LLM.
- [ ] Scoring de pertinence / tri par importance.
- [ ] Détection de doublons sémantiques (deux sources qui parlent du
      même événement).
- [ ] Alertes sur mots-clés (email, Discord, Slack).
- [ ] Interface web de consultation (au-delà d'une simple API JSON).
- [ ] Tags automatiques générés à partir du contenu.

## 🗺️ Étapes de réalisation

### 🔸 Phase 1 — Cadrage
- [ ] Choisir la stack technique définitive.
- [ ] Lister au moins 3 à 5 sources fiables par catégorie
      (cybersécurité / informatique / IA agentique).
- [ ] Définir le format de restitution visé (API seule ? dashboard ?
      les deux ?).

### 🔸 Phase 2 — Setup du projet
- [ ] Initialiser le repo Git et la structure du projet.
- [ ] Mettre en place la base de données et son schéma (table
      `Article` : id, titre, lien unique, résumé, source, catégorie,
      date de publication, date de collecte).

### 🔸 Phase 3 — Collecte des données
- [ ] Écrire la fonction de collecte pour un flux RSS.
- [ ] Généraliser pour parcourir toutes les sources de toutes les
      catégories.
- [ ] Gérer le dédoublonnage (vérifier l'existence via le lien avant
      insertion).

### 🔸 Phase 4 — Automatisation
- [ ] Planifier une collecte périodique (ex. toutes les heures).
- [ ] Gérer les erreurs (flux indisponible, timeout) sans bloquer les
      autres sources.

### 🔸 Phase 5 — Exposition des données
- [ ] Endpoint pour lister les articles avec filtres (catégorie,
      source, mot-clé, pagination).
- [ ] Endpoint pour lister les catégories et sources disponibles.

### 🔸 Phase 6 — Interface de consultation
- [ ] Décider si une interface web est nécessaire pour ce projet ou si
      l'API suffit pour l'usage prévu.
- [ ] Si oui : page listant les articles avec filtres, mise à jour
      simple.

### 🔸 Phase 7 — Enrichissement (bonus)
- [ ] Résumé automatique / scoring / alertes selon les priorités.

### 🔸 Phase 8 — Déploiement & maintenance
- [ ] Héberger le service (VPS, PaaS, etc.).
- [ ] Mettre en place un minimum de supervision (logs de collecte,
      alerte si une source est en échec répété).

## ✅ Définition de "terminé" (Definition of Done)

- ✅ La collecte automatique fonctionne sans intervention manuelle.
- ✅ Les articles sont correctement classés par catégorie.
- ✅ Il est possible de retrouver un article par mot-clé et par catégorie.
- ✅ Aucun doublon n'apparaît après plusieurs cycles de collecte.

## 🔀 Workflow Git & collaboration

- 📦 Un repo GitHub dédié à ce projet, avec vous deux comme
  collaborateurs.
- 🌿 `main` reste toujours stable ; le travail se fait sur des branches
  `feature/nom-court` (ex. `feature/endpoint-filtrage`).
- 🔍 Une Pull Request par fonctionnalité ou par phase, relue par l'autre
  avant merge.
- 📋 Idéalement, chaque tâche de la roadmap devient une Issue GitHub ; la
  PR qui la résout la référence (`Closes #12`).
- 📝 Messages de commit clairs (ex. `feat: ajoute la collecte RSS`,
  `fix: corrige le dédoublonnage par lien`).

## 📊 Suivi & compte-rendu au mentor

À mettre à jour régulièrement (ex. avant chaque point avec le mentor) :

| Date | Fait | En cours | Bloquants | Prochaine étape |
|---|---|---|---|---|
| | | | | |

## 🌱 Pistes d'évolution futures

- 📰 Newsletter hebdomadaire générée automatiquement à partir des articles
  les plus pertinents.
- 🔗 Croisement avec le projet `tryhackme-scraper` (ex. signaler les
  nouvelles rooms THM comme un type de contenu de veille supplémentaire).
- ⭐ Système de favoris/lecture différée pour l'utilisateur.
