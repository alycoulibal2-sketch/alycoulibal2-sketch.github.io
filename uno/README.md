# Feuille de score UNO

**On note les points. On ne joue pas.** Pas de cartes à l'écran, pas de partie simulée :
c'est le carnet où l'on inscrit les scores d'une vraie partie de UNO, autour d'une vraie table.

Cinq joueurs par défaut — **Aly, Aïcha, Abdoul, Papa et Maman** — et un seul fichier,
`index.html`, qui s'ouvre dans n'importe quel navigateur. Dessiné pour le pouce sur un
iPhone 14 Pro Max (430 × 932, encoche et barre d'accueil comprises). Aucune dépendance,
aucun build, aucun serveur, aucun compte.

## L'installer sur l'iPhone (30 secondes)

En ligne ici : **https://alycoulibal2-sketch.github.io/uno/**

1. **Le lien** — ouvrir cette adresse dans Safari. C'est tout.
2. **Sur l'écran d'accueil** — bouton *Partager* → *Sur l'écran d'accueil*. L'appli s'ouvre
   alors en plein écran, sans barre d'adresse, avec son icône.
3. **Hors connexion** — envoyer `index.html` à l'iPhone (AirDrop, Fichiers, pièce jointe)
   et l'ouvrir. Tout fonctionne ; seules les polices retombent sur celles du système.

Servi par GitHub Pages depuis ce dossier. Pour l'avoir aussi **sans internet**, à la maison :
copier `index.html` sur un PC du réseau et le servir en local, par exemple avec
`python -m http.server 8080 --bind 0.0.0.0` — l'iPhone l'ouvre alors sur `http://<ip-du-pc>:8080`
(sous Windows, ouvrir le port 8080 en profil « Privé » dans le pare-feu).

## Noter une manche

1. **Nouvelle manche**.
2. Toucher **qui a posé sa dernière carte**.
3. Pour chaque autre joueur, taper les cartes qui lui restent en main. Le pavé propose les
   chiffres 0–9 et les cartes spéciales avec leur valeur : **+2 / ↻ / ⊘ = 20**,
   **Joker / +4 = 50**. Le total monte tout seul.
   - `Cartes` : chaque touche **ajoute** une carte (9 · 7 · +2 → 36).
   - `Total` : on tape directement le nombre quand on le connaît déjà.
   - `⌫` retire la dernière carte, `C` remet à zéro, `Suivant` passe au joueur d'après.
4. **Valider**. Le clavier iOS ne s'ouvre jamais : rien ne saute à l'écran pendant la saisie.

## Les deux façons de compter

Réglables dans *Réglages → Façon de compter*. Le basculement **recalcule toute la partie
déjà notée** : les cartes saisies sont conservées, seule la règle change.

| | Qui marque | Qui gagne |
|---|---|---|
| **Le gagnant marque** *(règle officielle)* | celui qui finit encaisse les mains adverses | premier à l'objectif |
| **Chacun ses points** | chacun ramasse ses propres cartes | le premier à l'objectif est éliminé, le plus petit score gagne |

Objectif au choix : 200, 300, 500 (défaut), 700 ou libre. En mode « chacun ses points »,
la jauge de chaque joueur vire à l'ambre puis au rouge à l'approche de la sortie.

## Le reste

- **Corriger** : *Historique* → toucher `M1`, `M2`… pour modifier ou supprimer une manche.
  Les totaux suivent.
- **Annuler** : le bouton en bas à gauche défait la dernière action, autant de fois qu'il faut.
- **Joueurs** : renommer, changer de couleur (toucher la pastille), faire sortir quelqu'un
  de table sans perdre ses points, en ajouter jusqu'à dix. Chacun porte une des quatre
  couleurs UNO, la cinquième personne héritant du joker multicolore.
- **Récap** : *Historique → Copier le récap* met le classement dans le presse-papiers.
- **Sauvegarde** : la partie vit dans le `localStorage` du téléphone. On peut fermer,
  éteindre, revenir : elle est là. Rien ne part sur internet.

## Détails techniques

Un fichier statique d'environ 64 Ko : HTML, CSS et JavaScript sans bibliothèque ni étape de
build. Polices *Archivo* et *Manrope* via Google Fonts, avec repli système. Zones sûres gérées
par `env(safe-area-inset-*)`, `viewport-fit=cover` et `100dvh` ; cibles tactiles ≥ 44 px ;
`prefers-reduced-motion` respecté ; icône d'écran d'accueil dessinée sur un canvas au chargement.
