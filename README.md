# 🧭 Voyage Roumanie 2026 — site de planification familial

Site mobile partagé pour organiser le voyage des 4 familles en Roumanie
(Bucarest + Carpates, 24 juillet → 3 août 2026).

- **Onglet Options** : toutes les activités avec photo, prix et temps de route.
- **Onglet La tournée (התוכנית שלנו)** : le plan décidé, classé par jour.
- **Synchro temps réel** entre les 4 familles via Supabase (toutes les 4 sec).

## 🚀 Mise en ligne (GitHub Pages)

1. Crée un repo public sur GitHub (ex. `voyage-roumanie`).
2. Pousse ce dossier (voir commandes ci-dessous).
3. Dans le repo : **Settings → Pages → Source : GitHub Actions**.
4. Le site se publie tout seul. URL : `https://TON-PSEUDO.github.io/voyage-roumanie/`

> Le workflow `.github/workflows/deploy.yml` redéploie automatiquement
> à **chaque push** sur la branche `main`.

## 💻 Commandes Git

Première mise en ligne :

```bash
cd ~/Desktop/voyage-roumanie
git init
git add .
git commit -m "Site voyage Roumanie"
git branch -M main
git remote add origin https://github.com/TON-PSEUDO/voyage-roumanie.git
git push -u origin main
```

Pour chaque correction ensuite :

```bash
git add .
git commit -m "fix: ce que j'ai changé"
git push
```

→ le site se rafraîchit automatiquement (~1 min après le push).

## 🗄️ Base de données (Supabase)

Les données du plan sont stockées dans la table `trip_plan`
(ligne `romania2026`) du projet Supabase. La clé utilisée est la clé
**publishable** (publique, sans risque dans le code d'une app web).

Pour changer de base, modifie `SB_URL` et `SB_KEY` en haut du `<script>`
dans `index.html`.

## 📝 Modifier les activités

La liste des activités est dans `index.html`, tableau `const ACT = [...]`.
Chaque entrée a : `title`, `desc`, `price`, `time`, `img`, `search`, `zone`.
