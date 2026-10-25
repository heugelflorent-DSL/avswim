# Passage d'Espadon Web sur Cloudflare Pages (compte gratuit)

## 1. Créer l'espace de stockage (KV)
Cloudflare → Storage & Databases → KV → Create :
- `espadon` (production)
- `espadon-test` (préversions)

## 2. Créer le projet Pages relié à GitHub
Workers & Pages → Create → Pages → Connect to Git → dépôt `heugelflorent-DSL/espadon-web`
- Production branch : `main`
- Framework preset : None ; Build command : (vide) ; Build output directory : `/`

## 3. Réglages du projet (Settings)
- Variables and Secrets (Production ET Preview) :
  - `ADMIN_EMAIL` = heugelflorent@gmail.com
  - `SESSION_SECRET` = une longue chaîne aléatoire (64 caractères)
- Bindings → KV namespace : nom de la liaison `ESPADON`
  - Production → `espadon` ; Preview → `espadon-test`
- Compatibility flags : `nodejs_compat` (Production et Preview)
Puis relancer un déploiement.

## 4. Migrer les comptes et analyses
1. Sur l'ancien site Netlify, connecté en super admin : Admin → « Exporter toutes les données » → fichier espadon-export.json
2. Sur le nouveau site : créer le compte super admin (même e-mail), se connecter, Admin → « Importer une sauvegarde »
3. Les entraîneurs gardent leur mot de passe.

## 5. Bascule
Vérifier le nouveau site, prévenir les entraîneurs de la nouvelle adresse (espadon-dsl.pages.dev ou proche), puis désactiver le site Netlify.
