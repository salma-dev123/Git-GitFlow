# 🧭 Guide de contribution

Bienvenue ! 🎉  
Ce document explique comment contribuer à ce projet et la **politique de branches** que nous suivons avec le modèle **Git Flow**.

---

## 🌳 Politique de branches

Notre workflow est basé sur le modèle **Git Flow**.  
Chaque type de branche a un rôle précis et des règles spécifiques. Merci de suivre ces conventions pour garder le projet propre et organisé.

### 🔹 Branche principale (main)
- Contient le code prêt pour la production.
- Toujours stable, testé et déployable.
- **Ne pas commit directement sur main.**
- Mise à jour uniquement via :
  - branches `release/*` pour les nouvelles versions
  - branches `hotfix/*` pour les corrections urgentes

### 🔹 Branche de développement (develop)
- Branche d’intégration pour le développement en cours.
- Contient les fonctionnalités approuvées avant la release.
- Toutes les branches `feature/*` y sont fusionnées.
- Base pour :
  - les branches `feature/*`
  - les branches `release/*`

### 🔹 Branches fonctionnalités (feature/*)
- Pour développer de nouvelles fonctionnalités ou améliorations.
- Toujours créées depuis `develop`.
- Fusionnées dans `develop` une fois terminées.
- **Convention de nommage** :  
  `feature/<description-courte-de-la-fonctionnalité>`  
  Exemples :  
  `feature/ajouter-page-login`  
  `feature/mettre-a-jour-navbar`
- **Commandes** :
```bash
git flow feature start ajouter-page-login
git flow feature finish ajouter-page-login
🔹 Branches release (release/*)
Préparent une nouvelle version du projet.

Créées depuis develop lorsque toutes les fonctionnalités prévues sont terminées.

Permettent tests, versioning et mise à jour de documentation avant le déploiement.

Fusionnées dans :

main → production

develop → inclure les changements de la release

Commandes :

bash
Copier le code
git flow release start v1.0.0
git flow release finish v1.0.0
🔹 Branches corrections urgentes (hotfix/*)
Pour corriger des bugs critiques en production.

Créées depuis main.

Fusionnées dans :

main → appliquer la correction immédiatement

develop → garder le développement à jour

Commandes :

bash
Copier le code
git flow hotfix start correction-login
git flow hotfix finish correction-login
🔹 Branches support (support/*)
Maintiennent d’anciennes versions encore utilisées.

Créées depuis un commit de release précédent sur main.

Rarement utilisées sauf pour un support long terme.

🧠 Résumé du workflow
arduino
Copier le code
main  ←── release/*  ←── develop  ←── feature/*
  ↑                        ↑
 hotfix/*              (nouvelles fonctionnalités)
Flux général : Issue → Feature Branch → Pull Request → Merge dans Develop → Release → Main

✅ Règles de contribution
Créer une issue avant de commencer une nouvelle fonctionnalité ou correction de bug.

Brancher depuis develop pour les nouvelles fonctionnalités.

Brancher depuis main pour les hotfix urgents.

Toujours rédiger des messages de commit clairs :

csharp
Copier le code
[Feature] Ajouter l’authentification utilisateur
[Fix] Correction de l’API pour les données utilisateurs
Ouvrir une Pull Request (PR) pour fusionner votre branche.

Attendre la revue et l’approbation avant de merger.

Maintenir votre branche synchronisée avec develop :

bash
Copier le code
git pull origin develop
Supprimer les branches après fusion pour garder le dépôt propre.

🧩 Exemple Git Flow
bash
Copier le code
# Démarrer une nouvelle fonctionnalité
git flow feature start ajouter-auth-utilisateur

# Travailler et commit
git add .
git commit -m "Ajouter le système d'authentification utilisateur"

# Terminer et fusionner la feature
git flow feature finish ajouter-auth-utilisateur

# Démarrer une release
git flow release start v1.0.0
git flow release finish v1.0.0
💡 Conseils
Ne travaillez jamais directement sur main ou develop.

Utilisez des branches petites et ciblées.

Synchronisez-vous régulièrement avec le dépôt distant pour éviter les conflits.

Taguez correctement les releases avec le versioning sémantique (v1.0.0, v1.1.0, etc.).

Utilisez des noms de branches et messages de commit significatifs.

📜 Licence
En contribuant, vous acceptez que vos contributions soient sous licence selon la licence existante du projet.

🤝 Merci
Vos contributions aident à maintenir ce projet solide, organisé et professionnel.
Bienvenue à bord 🚀