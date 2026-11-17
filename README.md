# Niayes Smart Dépôt – plateforme de commande (version 1)

Site statique : un catalogue, un panier, et une commande envoyée sur WhatsApp.
Aucun serveur, aucun coût d’hébergement.

## Fichiers
- `index.html` : le site (catalogue, panier, formulaire de commande)
- `images/` : `logo.png` et `hero.jpg` (visuel d’illustration du projet, à remplacer par de vraies photos avant le lancement)
- `products.json` : **le catalogue et les réglages**. Seul fichier à modifier au quotidien.

## Mise en ligne (10 minutes)
1. Créez un compte GitHub puis un dépôt `niayes-smart-depot`.
2. Envoyez-y `index.html`, `products.json` et ce `README.md` (bouton *Add file → Upload files*).
3. *Settings → Pages → Branch : main, dossier : / (root) → Save*.
4. Votre site est disponible à `https://VOTRE-PSEUDO.github.io/niayes-smart-depot/`.
5. Pour tester en local : `python -m http.server` dans le dossier, puis ouvrez `http://localhost:8000`.
   (Ouvrir `index.html` directement par double-clic ne charge pas le catalogue.)

## Qui peut ajouter des produits ?
Uniquement les personnes qui ont le droit d’écrire dans le dépôt, donc vous.
1. Sur GitHub, ouvrez `products.json`, cliquez sur le crayon.
2. Copiez un bloc `{ ... }` existant, changez `id` (unique, sans espace), `nom`, `prix`, etc.
3. *Commit changes* : le site se met à jour en 1 à 2 minutes.

Pour retirer un produit sans le supprimer : `"dispo": false`.

**Sécurité** : activez la double authentification (2FA) sur votre compte GitHub et n’ajoutez aucun collaborateur en qui vous n’avez pas confiance.

## Réglages (bloc `config`)
- `whatsapp` : votre numéro, format international sans « + » (ex. `221771234567`). **À remplacer.**
- `livraison` / `gratuite_des` / `commande_min` : frais de livraison, seuil de livraison offerte, commande minimale (FCFA).
- `delai_jours` : délai minimum avant livraison.

Les prix du fichier sont des **exemples**. Fixez-les avec vos vrais coûts d’achat.

## Limites de cette version (à connaître)
- Pas de comptes clients, pas de paiement en ligne, pas de décompte automatique du stock : la commande arrive par WhatsApp et vous confirmez à la main.
- Le catalogue est public (c’est normal pour une vitrine).

## Version 2 (quand les commandes arrivent)
Passer à une base de données avec connexion administrateur (ex. Supabase, offre gratuite) : tableau de bord des commandes, stock en temps réel, comptes pour restaurants et hôtels, paiement Wave / Orange Money. À faire seulement après avoir validé la demande avec la version 1.

## Ajouter des photos de produits
1. Déposez la photo dans `images/` (ex. `images/oignon.jpg`, carrée, 600×600 px, moins de 150 Ko).
2. Dans `products.json`, ajoutez au produit : `"image": "images/oignon.jpg"`.

## Textes à valider avant le lancement
Les réponses de la section « Questions fréquentes » (paiement, conservation, remplacement) décrivent le service visé. Gardez-les seulement si elles sont vraies le jour du lancement.
