# japan

Single page HTML déployée automatiquement sur GitHub Pages.

## Structure

```
src/                  # contenu publié (dépose ton index.html ici)
.github/workflows/    # pipeline de déploiement
```

Seul le contenu de `src/` est publié. Le reste du dépôt (README, workflow) n'est pas exposé.

## Déploiement

Chaque push sur `main` déclenche le workflow `deploy.yml`, qui publie `src/` sur GitHub Pages.
Le job échoue volontairement si `src/index.html` est absent, pour éviter de mettre en ligne un site vide.

Déclenchement manuel possible : onglet **Actions** → *Deploy to GitHub Pages* → **Run workflow**.

## Configuration initiale (une seule fois)

Dans **Settings → Pages** du dépôt GitHub, régler **Source** sur **GitHub Actions**.

## Domaine personnalisé (optionnel)

Ajouter un fichier `src/CNAME` contenant le domaine (ex. `japan.example.com`), puis configurer
le DNS chez le registrar.
