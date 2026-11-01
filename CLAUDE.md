# Consignes pour Claude

## Branches et déploiement (à suivre à chaque tâche)

Le workflow « Pages (main + branch previews) » publie chaque branche sur GitHub Pages :
- branche de travail (`claude/…`) → `https://adrien426.github.io/Fc27/preview/<branche>/`
- `test` → `https://adrien426.github.io/Fc27/preview/test/` (version de test)
- `main` → `https://adrien426.github.io/Fc27/` (version en ligne)

À chaque tâche :
1. Travailler sur sa branche de travail et pousser (la preview de la branche se met à jour).
2. Une fois terminé, **fusionner la branche dans `test`** et pousser `test` :
   ```
   git fetch origin test && git checkout -B test origin/test   # ou origin/main si test n'existe pas
   git merge --no-ff <branche-de-travail>
   git push -u origin test
   ```
   Ne jamais forcer (`--force`) sur `test` ni `main`.
3. Donner le lien de test et dire ce qu'il faut vérifier.
4. **Ne fusionner `test` dans `main` que lorsque l'utilisateur a validé le test.**

Pas de pull request sans demande explicite.
