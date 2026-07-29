# POP-BEAT

Un pop-it musical à jouer dans le navigateur (mobile ou desktop). Grille de bulles à éclater ; chaque bulle joue la note suivante d'une mélodie 8-bit.

## Lancer

Ouvre `index.html` dans un navigateur.

## Installer comme appli sur mobile (PWA)

Le projet est une PWA (manifeste + service worker + icône) : il s'installe et s'ouvre en plein écran, avec une icône sur l'écran d'accueil, et fonctionne hors-ligne. L'installation nécessite un hébergement HTTPS — GitHub Pages le fait gratuitement.

### Mise en ligne via GitHub Pages

1. Crée un dépôt sur https://github.com/new — nom `pop-beat`, visibilité **Public** (requis pour Pages gratuit), sans README.
2. Depuis le dossier du projet, pousse les fichiers (remplace `TON-PSEUDO`) :

   ```
   git init
   git add .
   git commit -m "POP-BEAT — pop-it musical PWA"
   git branch -M main
   git remote add origin https://github.com/TON-PSEUDO/pop-beat.git
   git push -u origin main
   ```

3. Sur le dépôt → **Settings** → **Pages** → Source : *Deploy from a branch* → Branch : **main** / **/(root)** → **Save**.
4. Après ~1 minute, l'appli est en ligne à `https://TON-PSEUDO.github.io/pop-beat/`.

### Installer sur le téléphone

Ouvre l'adresse GitHub Pages sur le mobile :

- Android (Chrome) : menu ⋮ → « Installer l'application ».
- iPhone (Safari) : Partager → « Sur l'écran d'accueil ».

Les chemins du projet sont relatifs, donc tout fonctionne sous le sous-dossier `/pop-beat/` (icône, manifeste, service worker, mode hors-ligne).

### Test rapide en local (sans installation)

Sur le même Wi-Fi : depuis le dossier, lance `python -m http.server 8000`, puis ouvre `http://IP-DE-TON-PC:8000` sur le téléphone.

## Fonctionnalités

- Grille 5×5 responsive, refill automatique (toujours au moins 10 bulles gonflées, tirage aléatoire, la bulle qu'on vient d'éclater est exclue).
- Son 8-bit ; chaque pop avance la mélodie choisie.
- 3 thèmes complets (Lavande, Sombre, Bleu) — fond + couleur des bulles.
- 10 mélodies du domaine public (Beethoven, Mozart, Grieg, Rossini, Joplin, Greensleeves, Korobeïniki…).
- Le thème et la dernière musique choisie sont mémorisés par le navigateur (localStorage).
