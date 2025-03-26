# Prérequis

Avant de commencer, assurez-vous d'avoir les versions suivantes installées :

- **PostgreSQL** : v17
- **Node.js** : v22.14.0
- **.NET** : Assurez-vous d'avoir la dernière version stable installée
- **Python**: Assurer-vous d'avoir la version 3.10.12 ou supérieur

# Installation du projet

## 1. Cloner les dépôts

Clonez le repository du frontend :
```sh
 git clone https://github.com/ArtKaody/frontend-save.git
```

Clonez le repository du backend-socket :
```sh
 git clone https://github.com/ArtKaody/backend-socket.git
```

Clonez le repository du  backend-Asp.Net :

```bash
git clone https://github.com/ArtKaody/backend-Asp.Net.git

```
Clonez le repository du  backend-affectation :

```bash
git clone https://github.com/ArtKaody/backend-affectation.git

```


## 2. Lancer le projet

### Démarrer le backend

installer en priorite backend socket pour le backend principale

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
#Pour le mot de passe changer "root" avec votre mot de passe lors de l'installation de postgres 
#Et pour la base de donne, changer G_A avec le nom de votre base de donne 
# DATABASE_URL="postgresql://<postgres>:root@localhost:5432/<G_A>?schema=public"


DATABASE_URL="postgresql://postgres:root@localhost:5432/G_A?schema=public"
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


############ Backend-Asp.Net 

### 1. accédez au dossier du projet :
```bash
cd backend-Asp.Net
```

### 2. Pour installer dotnet et tous les dependances 

Il faut d'abord installer .Net version 6.0 ou plus 

et pour installer tous les dependances 
```bash
dotnet restore
```



### 3. Configurer la base de données PostgreSQL

Assurez-vous que PostgreSQL est installé et en cours d'exécution.


Modifiez le fichier appsettings.json pour y renseigner vos informations de connexion PostgreSQL :
Remplacez "G_A" par votre nom de base de donne  PostgreSQL.
Remplacez "postgres" par nom d'utilisateur PostgreSQL.
Remplacez "VotreMotDePasse" par votre mot de passe PostgreSQL.
```bash

"ConnectionStrings": {
    "DefaultConnection": "Host=localhost;Port=5432;Database=gestion_achat;Username=postgres;Password=VotreMotDePasse"
}

```

🔹 Remarque : 

### 4.Pour démarrer le serveur

```bash
dotnet run
```

#################### Service python
### 1. accédez au dossier du projet :
```bash
cd backend-affectation
```

### 2. Pour installer tous les dependances  

```bash
pip install fastapi uvicorn sqlalchemy psycopg2-binary
pip install alembic
pip install asyncpg sqlalchemy psycopg2
pip install pydantic-settings
ouvrez le dossier src/core/config.py et suivez les instructions dans le commentaire
```


### Démarrer le frontend

1. Accédez au dossier frontend :
```sh
cd frontend-save
```
2. Installez les dépendances :
```sh
npm install
```
3. Démarrez l'application :
```sh
npm run dev
```

### Démarrer le service du python:
```sh
uvicorn src.api.main:app --reload
```

Votre projet est maintenant accessible et fonctionnel ! 🚀

