# Don de sang, don de vie — EMI Khayr

- `index.html` : **formulaire des élèves** (nom, année, filière uniquement).
- `organisateurs.html` : **espace organisateurs** (effectifs, noms, suppression, simulation), protégé par un code.
- `google-script/Code.gs` : petit programme Google qui **reçoit les dons** dans une feuille Google Sheets.
- `logo.jpg`, `fond.jpg` : images.

## 1. Mettre le site en ligne (GitHub Pages)
Settings → Pages → Deploy from a branch → `main` / `(root)` → Save.

## 2. Recevoir les dons automatiquement (Google Sheets + Apps Script)
1. Allez sur https://sheets.new (créez une feuille Google vide, nommez-la « Dons de sang »).
2. Menu **Extensions → Apps Script**. Effacez le code existant et collez tout le contenu de `google-script/Code.gs`.
3. Remplacez `CHANGEZ-MOI` par **votre code organisateur** (un mot de passe de votre choix), puis enregistrez (icône disquette).
4. Cliquez sur **Déployer → Nouveau déploiement**. Type : **Application Web**. *Exécuter en tant que* : **Moi**. *Qui a accès* : **Tout le monde**. Cliquez sur **Déployer**.
5. Autorisez l’accès quand Google le demande (si un avertissement « application non validée » apparaît : **Paramètres avancés → Accéder à … (non sécurisé)**, c’est votre propre script).
6. Copiez l’**URL de l’application Web** (elle se termine par `/exec`).
7. Sur GitHub, ouvrez `index.html` → icône crayon → remplacez `const API_URL="";` par `const API_URL="VOTRE_URL";` → **Commit changes**. Faites **la même chose dans `organisateurs.html`**.
8. Ouvrez la page organisateurs : saisissez votre code. Les dons des élèves apparaissent (la page se met à jour toute seule toutes les 30 secondes, ou avec « Actualiser »).

Si vous modifiez plus tard le code du script, refaites **Déployer → Gérer les déploiements → modifier → Nouvelle version**.

## À savoir
- Tous les dons sont aussi visibles dans votre feuille Google Sheets (onglet « Donneurs »).
- N’importe qui connaissant le lien du formulaire peut envoyer un don : relisez la liste avant d’annoncer les chiffres.
- Sans `API_URL`, les pages fonctionnent en mode simple (message WhatsApp à importer à la main).
