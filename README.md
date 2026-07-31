# POP-BEAT

Un pop-it musical à jouer dans le navigateur (mobile ou desktop). Éclate les bulles : chaque pop joue la note suivante de la mélodie choisie, avec des sons synthétisés au style « liquid glass ».

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

- Deux modes de jeu : **grille** 5×5 (toujours au moins 10 bulles gonflées, refill aléatoire) et **rapide** (5 bulles à la fois qui réapparaissent aussitôt éclatées).
- Plusieurs sons synthétisés au choix : **Bulle** (signature), Bulle douce, Bulle profonde, **Éclat** (percussif), 8-bit, Électro, Piano.
- 3 thèmes « liquid glass » — **Bleu** (par défaut), Lavande, Sombre — chacun définissant le fond et la couleur des bulles.
- Une vingtaine de mélodies : une **signature originale** plus des airs du domaine public (classiques, folk, gospel).
- Retour haptique à chaque pop ; **secouer** le téléphone regonfle toutes les bulles et remet la mélodie à zéro.
- Interface responsive, grille placée en bas pour le confort à une main.
- Le thème, la dernière musique et l'effet sonore choisis sont mémorisés par le navigateur (localStorage).

## Format des notes

Les mélodies sont des suites de noms de notes anglais : `C`=do, `D`=ré, `E`=mi, `F`=fa, `G`=sol, `A`=la, `B`=si. `#` pour un dièse, le chiffre = octave (4 = médium). Exemple : `C5 E5 G5 A5`.
