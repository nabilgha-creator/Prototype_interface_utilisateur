# Prototype Interface Utilisateur — Rick & Morty

## Description

Projet front-end réalisé en équipe : création d’un prototype d’interface utilisateur en **React (Vite)** consommant une **API publique**.
L’application récupère des personnages de l’univers **Rick & Morty**, permet de **filtrer** les résultats et d’afficher un **détail** au clic sur une vignette.

## API utilisée

* **Rick and Morty API** : `https://rickandmortyapi.com/`

## Fonctionnalités implémentées

* Connexion à l’API (appel HTTP)
* Affichage des données dans la page
* Gestion asynchrone du chargement (état `loading`)
* Gestion simple des erreurs (état `error`)
* Liste de personnages (vignettes)
* Détail d’un personnage sélectionné
* Filtres via menus déroulants :

  * Status (alive / dead / unknown)
  * Gender (female / male / genderless / unknown)
  * Species (Human / Alien / Humanoid / Mythological Creature)
* Pagination (sélecteur de page)
* Navigation vers la section détail via ancre (`#detail`)
* Découpage en composants (ex : `CharacterGrid`, `CharacterCard`, `CharacterDetail`, etc.)

## Installation

### Prérequis

* **Node.js** 
* **npm**

### Étapes

```bash
# 1) Installer les dépendances
npm install

# 2) Lancer le serveur de dev
npm run dev
```

Puis ouvrir l’URL indiquée dans le terminal (souvent `http://localhost:5173`).

> ⚠️ Si PowerShell bloque npm (ExecutionPolicy), lancer le terminal en **Command Prompt (cmd)** dans VS Code, ou utiliser :
>
> ```bash
> npm.cmd run dev
> ```

## Scripts utiles

```bash
npm run dev      # lance le projet en mode développement
npm run build    # build de production
npm run preview  # aperçu du build
```

## Structure du projet (exemple)

```
src/
  App.jsx
  App.css
  composants/
    CharacterGrid.jsx
    CharacterCard.jsx
    CharacterDetail.jsx
    loader.jsx        (si utilisé pour l’appel API)
  hooks/              (optionnel)
    useCharacters.js  (optionnel)
```

## Notes techniques

* Les requêtes sont faites via `fetch` (asynchrone) dans un `useEffect`.
* Les filtres/pagination construisent une query string via `URLSearchParams`.
* L’affichage est protégé contre les cas où `results` est vide (évite les crashs).
