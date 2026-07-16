# Le Vault — Plateforme d'apprentissage & suivi

Plateforme personnelle d'apprentissage et de suivi, bâtie sur le **plan de reconstruction cérébrale**.
Six couloirs (Acoustique, Sonorisation, DJ, MAO/Reaper, Piano, Chant), une bibliothèque de
1080 exercices MIDI jouables et téléchargeables, des antisèches imprimables, des formulaires
DJ par client, et un espace enseignement.

Le site est **entièrement statique** : une fois les fichiers en ligne, il fonctionne tout seul,
sans serveur ni base de données. Toute ta progression est enregistrée dans ton navigateur.

---

## Mettre le site en ligne — sans aucune ligne de commande

Tout se fait à la souris, depuis le site de GitHub et celui de Cloudflare. Aucune installation,
aucun terminal. Compte deux dossiers dans le ZIP fourni :

- **`dist/`** — le site déjà construit, prêt à héberger. **C'est celui-ci qu'on met en ligne.**
- le reste (dossiers `src`, `scripts`, etc.) — le code source, utile seulement si tu veux
  modifier le site plus tard. Tu peux l'ignorer pour un simple déploiement.

### Étape 1 — Créer un compte et un dépôt GitHub

1. Va sur **github.com** et crée un compte (gratuit) si tu n'en as pas.
2. En haut à droite, clique sur le **+** puis **New repository**.
3. Donne-lui un nom, par exemple `le-vault`.
4. Laisse-le en **Public** (ou Private, les deux marchent avec Cloudflare).
5. Coche **Add a README file** (peu importe, on le remplacera).
6. Clique **Create repository**.

### Étape 2 — Envoyer les fichiers du site (glisser-déposer)

1. Sur la page de ton dépôt, clique sur **Add file** → **Upload files**.
2. Ouvre le dossier **`dist`** sur ton ordinateur.
3. Sélectionne **tout ce qu'il y a à l'intérieur** de `dist` (les fichiers *et* les
   sous-dossiers `assets`, `midi`, `notes`), puis **glisse-les** dans la zone d'upload
   de la page GitHub.
   > ⚠️ Glisse le **contenu** de `dist`, pas le dossier `dist` lui-même — il faut que
   > `index.html` se retrouve à la racine du dépôt.
   >
   > Le dossier `midi` contient beaucoup de fichiers : l'upload peut prendre quelques minutes.
   > Si ton navigateur peine, tu peux glisser les sous-dossiers en deux ou trois fois
   > (d'abord `index.html` + `assets` + `_headers` + `_redirects`, puis `midi`, puis `notes`).
4. En bas, laisse le message par défaut et clique **Commit changes**.

### Étape 3 — Publier avec Cloudflare Pages

1. Va sur **dash.cloudflare.com** et crée un compte gratuit.
2. Dans le menu de gauche : **Workers & Pages** → bouton **Create** → onglet **Pages**
   → **Connect to Git**.
3. Autorise Cloudflare à accéder à GitHub, puis choisis ton dépôt `le-vault`.
4. À l'écran de configuration, comme le site est **déjà construit**, laisse
   **Build command vide** et mets **Build output directory** sur `/` (la racine).
   *(Framework preset : « None ».)*
5. Clique **Save and Deploy**.

Au bout d'une minute, Cloudflare te donne une adresse du type
`https://le-vault.pages.dev` — ton site est en ligne. 🎉

À chaque fois que tu re-glisseras des fichiers mis à jour sur GitHub (Étape 2),
Cloudflare republiera tout seul.

---

## Mettre à jour un contenu plus tard (toujours sans commande)

Tout ce que tu vois à l'écran (progression, élèves, séances) vit dans ton navigateur :
rien à redéployer pour ça.

Pour changer un **texte, un exercice ou un formulaire**, il faut modifier le code source
et reconstruire le site — ça, ça demande soit un développeur, soit l'outil en ligne
**StackBlitz** (stackblitz.com), qui ouvre le projet dans le navigateur, permet de
l'éditer et de retélécharger un nouveau dossier `dist`, sans rien installer. Si tu veux,
je peux te préparer un guide pas-à-pas pour cette partie le moment venu.

---

## Ce que contient la plateforme

- **Tableau de bord** — les 7 principes du protocole, la semaine périodisée à cocher,
  le journal de séance avec métrique objective et courbe de tendance.
- **Couloirs** — les 6 domaines, leurs phases à cocher, et pour chacun des exercices
  guidés avec la métrique à mesurer.
- **Oreille** — 1080 exercices MIDI : écoute en un clic dans le navigateur *ou*
  téléchargement du fichier `.mid` pour Reaper. Tempo réglable, suivi de complétion.
- **Antisèches** — condensés de cours (sono, table de mixage, VideoPsalm, transitions DJ),
  imprimables pour la régie ou la transmission.
- **Formulaires DJ** — deux variantes (standard, cérémonie chrétienne), en-tête au nom
  du couple, impression A4 propre (l'interface disparaît à l'impression).
- **Enseignement** — bascule en haut à droite : ajoute des élèves, assigne des exercices,
  suis l'avancement. (Données locales pour l'instant ; conçu pour ouvrir aux comptes réels plus tard.)

---

## Bon à savoir

- **Le son démarre au premier clic** sur un bouton « Écouter » — c'est une règle normale
  des navigateurs, aucun réglage à faire.
- **Rien ne quitte l'appareil** : la progression est stockée localement. Sur un autre
  ordinateur ou navigateur, elle repart de zéro. Le bouton **Réinitialiser** (bas du
  tableau de bord) efface tout.
- Le site marche aussi bien sur ordinateur que sur mobile.

---

## Note d'honnêteté (protocole)

Aucune méthode ne « débloque » une capacité cérébrale latente ni n'augmente le QI général :
le transfert entre tâches est faible. Ce qui fonctionne est cumulatif — pratique profonde d'un
domaine, condition physique, sommeil, exposition graduée au stress, attention — et compose, sur
des années, la prise de décision experte par reconnaissance. Cette plateforme est un outil de
discipline et de mesure, pas un raccourci.
