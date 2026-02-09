# 🚀 Guide de Configuration Directus pour Zurie Studio

## Option 1 : Directus Cloud (Recommandé - Plus Simple) ⭐

### Étapes :

1. **Créer un compte Directus Cloud**
   - Allez sur : https://directus.cloud/register
   - Créez un compte gratuit (14 jours d'essai)
   - Créez un nouveau projet

2. **Récupérer vos informations**
   - Une fois le projet créé, vous obtiendrez :
     - **DIRECTUS_URL** : `https://votre-projet.directus.app`
     - Vous devrez créer un **DIRECTUS_SERVER_TOKEN** (voir étape suivante)

3. **Générer un token admin statique**
   - Connectez-vous à votre instance Directus Cloud
   - Allez dans **Settings** > **Users & Roles**
   - Cliquez sur l'utilisateur **Admin**
   - Faites défiler jusqu'à **Token**
   - Cliquez sur **Generate Token**
   - **Copiez le token** (c'est votre `DIRECTUS_SERVER_TOKEN`)
   - **IMPORTANT** : Cliquez sur **Save** pour sauvegarder l'utilisateur

4. **Configurer le fichier .env**
   - Copiez `.env.example` en `.env` :
     ```bash
     copy .env.example .env
     ```
   - Éditez le fichier `.env` et remplissez :
     ```env
     DIRECTUS_URL="https://votre-projet.directus.app"
     DIRECTUS_SERVER_TOKEN="votre_token_admin_copié"
     NUXT_PUBLIC_SITE_URL="http://localhost:3000"
     ```

5. **Appliquer le template Zurie Studio**
   - Ouvrez un terminal dans le projet
   - Exécutez :
     ```bash
     npx directus-template-cli@latest apply
     ```
   - Choisissez le template **Agency OS** (Zurie Studio est basé dessus)
   - Entrez votre URL Directus
   - Entrez votre token admin
   - Attendez la fin du processus

6. **Démarrer le serveur Nuxt**
   ```bash
   npm run dev
   ```

---

## Option 2 : Installer Docker Desktop (Pour développement local)

### Prérequis :
- Windows 10/11 avec WSL2 activé
- Au moins 4GB de RAM disponible

### Étapes :

1. **Installer Docker Desktop**
   - Téléchargez depuis : https://www.docker.com/products/docker-desktop/
   - Installez Docker Desktop
   - Redémarrez votre ordinateur si nécessaire
   - Vérifiez l'installation :
     ```bash
     docker --version
     ```

2. **Démarrer Directus avec Docker**
   ```bash
   cd .directus
   docker compose up
   ```

3. **Accéder à Directus**
   - Ouvrez : http://localhost:8055
   - Créez votre compte admin
   - Suivez les étapes 3-6 de l'Option 1

---

## ⚠️ Notes Importantes

- **Directus Cloud** offre 14 jours d'essai gratuit, puis payant
- **Docker** est gratuit mais nécessite plus de configuration
- Pour le développement, **Directus Cloud** est recommandé car plus simple
- Assurez-vous que votre fichier `.env` est bien créé et configuré avant de démarrer Nuxt

---

## 🔧 Dépannage

### Erreur "Unable to load redirects"
- Normal si Directus n'est pas démarré ou mal configuré
- Vérifiez que `DIRECTUS_URL` dans `.env` est correct
- Vérifiez que Directus est accessible dans votre navigateur

### Erreur "Invalid token"
- Vérifiez que vous avez bien sauvegardé l'utilisateur après avoir généré le token
- Régénérez le token si nécessaire

### Le site ne se connecte pas à Directus
- Vérifiez que le fichier `.env` existe bien
- Vérifiez que les variables sont correctes (sans espaces, avec guillemets)
- Redémarrez le serveur Nuxt après avoir modifié `.env`
