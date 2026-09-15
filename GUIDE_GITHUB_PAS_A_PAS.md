# Guide pas à pas — Simulateur Forever CIV sur GitHub Pages

## Objectif
Publier le simulateur Forever CIV sur une adresse HTTPS gratuite afin qu'il fonctionne dans un vrai navigateur, puis l'installer sur l'écran d'accueil d'un iPhone ou d'un téléphone Android comme une application web.

## 1. Créer le compte GitHub
1. Aller sur `https://github.com/signup`.
2. Créer un compte personnel gratuit (ou utiliser une connexion sociale proposée par GitHub).
3. Choisir un nom d'utilisateur GitHub. Exemple : `francois-forever`.
4. Vérifier l'adresse e-mail demandée par GitHub.
5. La double authentification (2FA) est recommandée pour sécuriser le compte.

## 2. Créer le dépôt du simulateur
1. Une fois connecté à GitHub, utiliser le bouton `+` puis `New repository`.
2. Nom conseillé : `forever-civ`.
3. Description facultative : `Simulateur mobile des tarifs Forever CIV`.
4. Choisir `Public` si vous utilisez GitHub Free et souhaitez GitHub Pages sans configuration payante.
5. Cliquer sur `Create repository`.

## 3. Envoyer les fichiers de l'application
Il faut envoyer **les fichiers décompressés**, pas le ZIP lui-même.

À la racine du dépôt, on doit voir :

```text
index.html
manifest.webmanifest
sw.js
.nojekyll
README.md
GUIDE_GITHUB_PAS_A_PAS.md
icons/
  apple-touch-icon.png
  icon-192.png
  icon-512.png
```

### Méthode la plus simple depuis le site GitHub
1. Ouvrir le dépôt.
2. Cliquer `Add file` > `Upload files`.
3. Sélectionner les fichiers et le dossier `icons` du pack décompressé.
4. Attendre la fin du chargement.
5. Saisir éventuellement le message `Première version du simulateur`.
6. Cliquer `Commit changes`.

**Contrôle important :** `index.html` doit être directement visible à la racine du dépôt, et non dans un sous-dossier supplémentaire.

## 4. Activer GitHub Pages
1. Dans le dépôt, ouvrir `Settings`.
2. Dans le menu de gauche, ouvrir `Pages`.
3. Sous `Build and deployment`, choisir `Deploy from a branch`.
4. Dans `Branch`, choisir `main`.
5. Dans le dossier, choisir `/(root)`.
6. Cliquer `Save`.
7. Attendre la publication. GitHub peut prendre quelques minutes.
8. Revenir dans `Settings > Pages` et utiliser `Visit site` quand le lien apparaît.

L'adresse ressemblera à :

```text
https://VOTRE-NOM.github.io/forever-civ/
```

## 5. Tester avant installation
Depuis le téléphone, ouvrir **l'adresse HTTPS GitHub Pages** — ne pas ouvrir `index.html` depuis l'app Fichiers.

Vérifier :
- les 6 boutons `Vente`, `PC`, `AA`, `A`, `MA`, `M` s'affichent ;
- la recherche affiche les produits ;
- `Ajouter`, `+`, `−` et `Supprimer` fonctionnent ;
- le total FCFA et le total CC changent ;
- le panier reste mémorisé après fermeture/réouverture ;
- après une première ouverture en ligne, l'application peut se rouvrir hors connexion grâce au cache PWA.

## 6. Installer sur iPhone
Utiliser de préférence Safari.
1. Ouvrir l'adresse GitHub Pages dans Safari.
2. Toucher `Partager`.
3. Choisir `Sur l'écran d'accueil`.
4. Activer `Ouvrir comme app web` si l'option est proposée.
5. Toucher `Ajouter`.
6. L'icône `Forever CIV` apparaît sur l'écran d'accueil.
7. Ouvrir l'application depuis cette icône.

## 7. Installer sur Android
Utiliser de préférence Chrome.
1. Ouvrir l'adresse GitHub Pages dans Chrome.
2. Ouvrir le menu `⋮`.
3. Choisir `Installer l'application`, ou selon la version de Chrome `Installer et créer un raccourci`.
4. Confirmer l'installation.
5. L'icône `Forever CIV` apparaît sur l'écran d'accueil / lanceur d'applications.

Le bouton `Installer` présent en haut du simulateur peut aussi déclencher la boîte d'installation sur Android lorsqu'elle est disponible. Sur iPhone, il affiche les instructions Safari.

## 8. Utiliser hors connexion
Le premier lancement doit être fait avec Internet afin que Safari/Chrome charge et mette en cache les fichiers. Ensuite, la version installée peut continuer à ouvrir le simulateur sans réseau pour les calculs, puisque les produits et prix sont intégrés à l'application.

## 9. Mettre les prix à jour plus tard
1. Modifier les fichiers localement ou remplacer `index.html` par une nouvelle version.
2. Dans le dépôt GitHub : `Add file > Upload files`.
3. Envoyer le fichier portant le même nom et valider `Commit changes`.
4. GitHub Pages republie automatiquement.
5. À la prochaine ouverture en ligne, l'application récupère la nouvelle version. Si un ancien écran reste affiché, fermer complètement l'app web puis la rouvrir, ou actualiser le site dans le navigateur.

## 10. Dépannage
### La page s'ouvre mais les produits ne fonctionnent pas
Vérifier que vous utilisez l'URL `https://...github.io/.../` et non un fichier `.html` ouvert dans Fichiers/Quick Look.

### Erreur 404
- vérifier que `index.html` est à la racine ;
- vérifier `Settings > Pages` : `main` + `/(root)` ;
- attendre quelques minutes après un commit.

### GitHub Pages ne propose pas de lien
- vérifier que l'e-mail GitHub est confirmé ;
- vérifier que le dépôt est public sur GitHub Free ;
- vérifier qu'au moins un commit contient `index.html`.

### L'application affiche encore une ancienne version
Actualiser la page en ligne. Le service worker est conçu pour rechercher la version réseau lors des navigations, tout en conservant une copie hors ligne.
