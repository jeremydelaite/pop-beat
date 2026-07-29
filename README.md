# POP-BEAT

Un pop-it musical à jouer dans le navigateur (mobile ou desktop). Grille de bulles à éclater ; chaque bulle joue la note suivante d'une mélodie 8-bit.

## Lancer

Ouvre `index.html` dans un navigateur.

## Installer comme appli sur mobile (PWA)

Le projet est une PWA (manifeste + service worker + icône) : il s'installe et s'ouvre en plein écran, avec une icône sur l'écran d'accueil, et fonctionne hors-ligne.

Pour que l'installation marche, la page doit être servie en HTTPS. Le plus simple :

1. Va sur https://app.netlify.com/drop
2. Glisse le dossier `POP-BEAT` entier dans la zone (aucun compte requis pour un test).
3. Netlify te donne une adresse https. Ouvre-la sur ton téléphone.
4. Android (Chrome) : menu ⋮ → « Installer l'application ». iPhone (Safari) : Partager → « Sur l'écran d'accueil ».

Autre option : héberger le dossier sur GitHub Pages.

Test rapide sur le même Wi-Fi (sans installation) : depuis le dossier, lance `python -m http.server 8000`, puis ouvre `http://IP-DE-TON-PC:8000` sur le téléphone.

## Fonctionnalités

- Grille 5×5 responsive, refill automatique (toujours au moins 10 bulles gonflées, tirage aléatoire, la bulle qu'on vient d'éclater est exclue).
- Son 8-bit ; chaque pop avance la mélodie choisie.
- 3 thèmes complets (Lavande, Sombre, Bleu) — fond + couleur des bulles.
- 10 mélodies du domaine public (Beethoven, Mozart, Grieg, Rossini, Joplin, Greensleeves, Korobeïniki…).
- Le thème et la dernière musique choisie sont mémorisés par le navigateur (localStorage).
