8. Workflow concret pour publier de nouvelles choses
8.1. Ajouter un nouvel article de recherche

Copier le PDF dans public/papers/ (par ex. public/papers/new-paper.pdf).

Dans src/pages/research.astro, ajouter une entrée dans le tableau papers :

{
  title: 'New paper on fuzzy Z-number navigation',
  venue: 'IEEE, 2025',
  file: '/papers/new-paper.pdf',
  tags: ['fuzzy logic', 'robot navigation'],
},


git add, git commit, git push.

Netlify rebuild → la nouvelle entrée apparaît.

8.2. Ajouter un nouveau cours / PPT

Exporter ton PPTX en PDF.

Copier les fichiers dans public/courses/, par exemple :

public/courses/ros2-webots-nav.pdf
public/courses/ros2-webots-nav.pptx


Ajouter l’objet correspondant dans le tableau courses de src/pages/courses.astro :

{
  title: 'Navigation ROS2 + Webots',
  desc: 'Slides du cours sur la navigation autonome sous ROS2 et Webots.',
  pdf: '/courses/ros2-webots-nav.pdf',
  pptx: '/courses/ros2-webots-nav.pptx',
},


Commit + push.

8.3. Ajouter un post de blog sur un projet IA

Créer un nouveau fichier dans src/pages/blog/, par exemple :

src/pages/blog/2025-11-10-rl-navigation-webots.md

Mettre un frontmatter + contenu :

---
title: "RL + Webots – première expérimentation"
date: "2025-11-10"
tags: ["webots", "reinforcement learning", "navigation"]
summary: "Petit log de mon premier essai de RL dans Webots sans ROS, puis avec ROS2."
---

Ici ton article :

- Contexte du projet.
- Setup (Ubuntu, WSL2, Webots, etc.).
- Idée du workflow (README, workflow GitHub, training, tests).
- Résultats, métriques, TODO, etc.


Commit + push → Netlify déploie → l’article apparaît automatiquement dans /blog.

8.4. Mettre à jour le CV

Remplacer public/cv/djeri-cv.pdf par la nouvelle version (même nom de fichier).

Commit + push.

Le site affiche automatiquement la nouvelle version.

9. Petit workflow Git basique (pour être propre)

Travailler sur une branche dev si tu veux tester :

git checkout -b feature/nom-fonctionnalite

Modifs → git commit → git push

Tu peux créer un Pull Request sur GitHub et le merger dans main pour déclencher Netlify.

Mais si c’est juste ton site perso, tu peux simplement travailler directement sur main :

git add .
git commit -m "Ajout d'un nouveau cours RL + Webots"
git push origin main

# Astro Starter Kit: Minimal

```sh
npm create astro@latest -- --template minimal
```

> 🧑‍🚀 **Seasoned astronaut?** Delete this file. Have fun!

## 🚀 Project Structure

Inside of your Astro project, you'll see the following folders and files:

```text
/
├── public/
├── src/
│   └── pages/
│       └── index.astro
└── package.json
```

Astro looks for `.astro` or `.md` files in the `src/pages/` directory. Each page is exposed as a route based on its file name.

There's nothing special about `src/components/`, but that's where we like to put any Astro/React/Vue/Svelte/Preact components.

Any static assets, like images, can be placed in the `public/` directory.

## 🧞 Commands

All commands are run from the root of the project, from a terminal:

| Command                   | Action                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Installs dependencies                            |
| `npm run dev`             | Starts local dev server at `localhost:4321`      |
| `npm run build`           | Build your production site to `./dist/`          |
| `npm run preview`         | Preview your build locally, before deploying     |
| `npm run astro ...`       | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help` | Get help using the Astro CLI                     |

## 👀 Want to learn more?

Feel free to check [our documentation](https://docs.astro.build) or jump into our [Discord server](https://astro.build/chat).
