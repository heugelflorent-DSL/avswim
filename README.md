# AVswim

Analyse vidéo de courses de natation (pointage image par image, fiches au format FFN, historique par nageur, comparatifs). Réalisé par Mat-et-Flo — Collectif alsacien pour la natation de demain.

- Site : https://avswim.pages.dev (Cloudflare Pages, branche `main` ; préversion de la branche `test`).
- Application : `index.html` (page unique). Serveur des comptes : `functions/api/[[path]].js`.
- Stockage : Cloudflare KV, liaison `AVSWIM` (`avswim` en production, `avswim-test` en préversion). Aucune vidéo n'est stockée.
- Variables : `ADMIN_EMAIL` (super admin), `SESSION_SECRET`. Option de compatibilité `nodejs_compat`.
