# Prérequis

Avant de commencer, assurez-vous d'avoir les versions suivantes installées :

- **PostgreSQL** : v17
- **Node.js** : v22.14.0
- **.NET** : Assurez-vous d'avoir la dernière version stable installée

# Installation du projet

## 1. Cloner les dépôts

Clonez le repository du frontend :
```sh
 git clone <URL_DU_REPO_FRONTEND>
```

Clonez le repository du backend-socket :
```sh
 git clone https://github.com/ArtKaody/backend-socket.git
```

## 2. Lancer le projet

### Démarrer le backend

############ Backend-socket 

1. Accédez au dossier backend-socket :
```sh
cd backend-socket
```
2. Installez les dépendances :
```sh
npm install
```
3.  Migration de la base de donne :
### verifier que vous aves creer une base de donne pour la gestion d'achat dans postgres 
 ouvrez pgadmin
 entrer votre mot de passe et creer une base de donne "G_A"

 ensuite dans le dossier backend-socket 
 creer un dossier .env

ensuite
copier dans .env

```sh
# Environment variables declared in this file are automatically made available to Prisma.
# See the documentation for more detail: https://pris.ly/d/prisma-schema#accessing-environment-variables-from-the-schema

# Prisma supports the native connection string format for PostgreSQL, MySQL, SQLite, SQL Server, MongoDB and CockroachDB.
# See the documentation for all the connection string options: https://pris.ly/d/connection-strings


#Changer "postgres" avec votre nom d'utilisateur dans postgres si c'est pars defaut vous garder comme le mien
#Pour le mot de passe changer avec votre mot de passe lors de l'installation de postgres "root"
#Et pour la base de donne, changer G_A avec le nom de votre base de donne 
DATABASE_URL="postgresql://<postgres>:<root>@localhost:5432/<G_A>?schema=public"
```
ensuite 

lancer la migration 

```sh
npx prisma migrate dev 
```

ecrire comme message "first migrate"

4. Démarrez le serveur :
```sh
npm run start
```

### Démarrer le frontend

1. Accédez au dossier frontend :
```sh
cd frontend
```
2. Installez les dépendances :
```sh
npm install
```
3. Démarrez l'application :
```sh
npm run dev
```

Votre projet est maintenant accessible et fonctionnel ! 🚀

