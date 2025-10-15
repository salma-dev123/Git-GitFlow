🧭 Clean Sync Cheatsheet – Étape par Étape

Ceci est ce que tu devras faire chaque jour pour garder tes branches propres et prêtes à être fusionnées (PR-ready).

🪜 Étape 1 : Mettre à jour develop et main en local
git fetch origin
git checkout develop
git pull --ff-only
git checkout main
git pull --ff-only


Explication / Pourquoi :

git fetch origin → Télécharge les derniers commits du dépôt distant sans fusionner.
Cela te permet de voir les mises à jour.

git checkout develop → Passe sur ta branche locale develop.

git pull --ff-only → Met à jour ta branche develop uniquement si elle peut avancer directement (sans commit de merge).

Même chose pour main.

Tâche à livrer :

✅ Ta branche locale develop et main doivent être exactement alignées avec celles du dépôt distant.
📸 Prends une capture d’écran du résultat de :

git log --oneline --graph


montrant que develop est alignée avec origin/develop.

🪜 Étape 2 : Rebaser ta branche feature sur un develop à jour
git checkout feature/321-recherche-filtrage
git rebase origin/develop
git push --force-with-lease


Explication / Pourquoi :

git checkout feature/... → Passe sur ta branche feature.

git rebase origin/develop → Replace tes commits au-dessus du dernier develop.
Cela garde un historique linéaire et réduit les risques de conflits.

Si Git s’arrête à cause de conflits :

git status               # pour voir les fichiers en conflit
# corrige les fichiers manuellement
git add path/to/file
git rebase --continue


git push --force-with-lease → Mets à jour ta branche distante de manière sécurisée après le rebase.

Tâche à livrer :

✅ Ta branche feature est entièrement rebasée.
📸 Prends une capture montrant que ta branche est en avance sur develop (avec tes commits).

🪜 Étape 3 : Corriger un rebase si quelque chose se passe mal
git rebase --abort


Explication :

Annule le rebase en cours si la situation devient trop compliquée.

Ta branche revient exactement à l’état avant le rebase.

Tâche à livrer :

✅ Montre (par une note ou capture) que tu comprends comment abandonner un rebase mal engagé.

🪜 Étape 4 : Back-Merge après une Release / Hotfix
git checkout develop
git merge --no-ff main
git push


Explication / Pourquoi :

Quand tu as terminé une release ou un hotfix sur main, tu dois le fusionner dans develop.

L’option --no-ff crée un commit de merge explicite, pour garder une trace claire du moment où la release a été intégrée.

Tâche à livrer :

✅ Simule ou explique le workflow de back-merge.
📸 Capture du commit de merge montrant main → develop.

🪜 Étape 5 : Préparation à la Pull Request (PR)

Rebase ta branche sur le dernier develop.

Vérifie que la CI est verte (tests et lint passent).

Ouvre une Pull Request vers develop.

Utilise Squash & Merge pour fusionner proprement.

💼 Résumé

Ces étapes garantissent :

un historique Git propre et linéaire,

des branches à jour,

et des PR claires et sans conflits.