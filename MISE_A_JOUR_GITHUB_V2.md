# Mise à jour GitHub — Forever CIV V2

Cette mise à jour ajoute :

1. **Mes simulations** : enregistrer plusieurs paniers avec un nom, puis les charger ou les supprimer.
2. **Devis / PDF** : saisir facultativement le nom du client, son téléphone et une observation, puis ouvrir un devis prêt à imprimer ou à enregistrer en PDF.
3. **WhatsApp** : ouvrir directement WhatsApp avec le détail du panier, le tarif, le total et le total CC.

## Mettre à jour le dépôt GitHub existant

1. Ouvrir le dépôt GitHub déjà utilisé pour Forever CIV.
2. Remplacer `index.html` par le nouveau fichier.
3. Remplacer `manifest.webmanifest`.
4. Remplacer `sw.js`.
5. Conserver `.nojekyll` et le dossier `icons/` tels quels, sauf si tu souhaites aussi les remplacer.
6. Valider avec **Commit changes**.
7. Attendre la republication de GitHub Pages.
8. Ouvrir l’application une première fois avec Internet.

## Si l’ancienne version reste affichée

Le nouveau `sw.js` utilise un cache `forever-civ-v2.0.0`, ce qui doit remplacer l’ancien cache automatiquement. Si le téléphone conserve malgré tout l’ancienne interface :

- fermer complètement l’application Forever CIV ;
- la rouvrir avec Internet ;
- si nécessaire, ouvrir l’adresse GitHub Pages dans le navigateur et actualiser la page ;
- en dernier recours, retirer l’icône de l’écran d’accueil puis réinstaller la PWA depuis la même adresse GitHub Pages.

## Sauvegardes

Les simulations enregistrées sont stockées **localement sur l’appareil**. Elles ne sont pas synchronisées entre plusieurs téléphones. Une future version pourra ajouter l’export/import des sauvegardes si nécessaire.
