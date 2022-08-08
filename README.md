# Projet Test technique E-commerce avec Airweb

## Présentation
Le but de ce projet est d'utiliser le back-end donné par l'entreprise (avec les objets) et de créer le front-end à partir de cela.
- Affichage des objets fournis dans le Back-end
- Afficher la liste des catégories fournis dans le Back-end
- Trier la liste d'objets suivant les catégories
- Ajouter les objets dans le panier au clique sur le logo d'ajout
- Affichage d'une page panier avec la liste récupérée dans le LocalStorage
- Affichage du nombre d'articles dans le panier (non acquis l'actualisation à l'instant T)


## Installation et lancement du Front-end & du Back-end
### Back-end
1. **Placement dans le dossier du Back-end**
```bash
cd server
```
2. **installation des dépendances NodeJS**
```bash
npm install
```
3. **Lancement du serveur Back-end sur le port 3000**
```bash
npm start
```
- Afin d'éviter de devoir relancer le serveur à chaque modification, on utilisera de préférence Nodemon
```bash
nodemon
```

### Front-end
1. **Cloner le dépot Github**
```bash
git clone https://github.com/Djoghlal/airweb-API.git
```

2. **Placement dans le dossier du Front-end**
```bash
cd front-end
```

3. **Lancement du serveur**
```bash
npm run serve
```

### AVERTISSEMENT
Le serveur front-end utilise des données sensibles, tel que l'url des catégories et des produits. Celles-ci ont été placées dans 
un fichier .env lui même placé dans le gitignore. Je joindrai le fichier .env en off de github de façon à garder cette sécurité.

### API développé avec les technologies suivantes
<img alt="NodeJS" src="https://img.shields.io/badge/node.js%20-%2343853D.svg?&style=for-the-badge&logo=node.js&logoColor=white"/>
<img alt="Vue.js" src="https://img.shields.io/badge/vuejs%20-%2335495e.svg?&style=for-the-badge&logo=vue.js&logoColor=%234FC08D"/>
<img alt="Bootstrap" src="https://img.shields.io/badge/bootstrap%20-%23563D7C.svg?&style=for-the-badge&logo=bootstrap&logoColor=white"/>
<img alt="Git" src="https://img.shields.io/badge/git%20-%23F05033.svg?&style=for-the-badge&logo=git&logoColor=white"/>

## Auteur
<img src='https://img.shields.io/badge/Autor-Djoghlal Mickaël-blue' />
<img src="https://img.shields.io/github/followers/MickaëlDjoghlal.svg?style=social&label=Follow&maxAge=2592000" />

## Licence 
<img src='https://forthebadge.com/images/badges/open-source.svg'/>