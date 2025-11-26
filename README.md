# DIGIY TABLES — Le Malraux

Mini-application PWA de réservation de tables pour le restaurant **Le Malraux**, intégrée à l'écosystème **DIGIYLYFE**.

- Réservation simple (date, heure, zone, personnes)
- Envoi automatique **Email + WhatsApp** au restaurant
- Aucune commission : relation directe client ↔ restaurant
- Interface optimisée mobile & PWA (installable comme une app)

## Structure du projet

```text
digiy-tables-malraux/
  ├── index.html
  ├── manifest.webmanifest
  ├── sw.js
  ├── icon-192.png
  └── icon-512.png
```

## Déploiement GitHub Pages

1. Copier ce dossier dans votre repo, par exemple :

```text
/beauville/digiy-hub/
  ├── index.html           ← DIGIY HUB (super app)
  └── digiy-tables-malraux/
       ├── index.html      ← cette app
       ├── manifest.webmanifest
       ├── sw.js
       ├── icon-192.png
       └── icon-512.png
```

2. Activer GitHub Pages sur la branche (ex: `main`) dans les settings.
3. L’URL sera du type :

```text
https://beauville.github.io/digiy-hub/digiy-tables-malraux/
```

4. Dans DIGIY HUB, pointer le module DIGIY TABLES vers cette URL :

```js
const LINKS = {
  tables: "https://beauville.github.io/digiy-hub/digiy-tables-malraux/"
};
```

## PWA

- `manifest.webmanifest` décrit l’app (nom, icônes, couleurs, start_url…).
- `sw.js` met en cache les fichiers principaux pour permettre :
  - un chargement rapide
  - un fonctionnement minimal hors-ligne (page déjà visitée).

Sur mobile, Chrome / Edge / Safari proposent ensuite **“Ajouter à l’écran d’accueil”**.

## Personnalisation rapide

- Changer l’email de réception dans `index.html` :

```js
const RESTO_EMAIL = 'digiylyfe@gmail.com';
```

- Changer le numéro WhatsApp du restaurant :

```js
const WA_NUMBER_FR = '33638329423';
```

- Adapter les horaires (midi / soir) dans le `<select name="heure">`.

---

Projet pensé pour être intégré au **DIGIY HUB** comme module `DIGIY TABLES`, 0% commission, au service du terrain.
