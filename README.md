# Projet example

## 🧐 À propos

ÉCRIRE QUELQUES LIGNES A PROPOS DU PROJET

**Date de création** : dd/mm/yyyy

## 📄 Documents

ℹ️ [Fiche projet Miro](https://miro.com/app/board/[BOARD_ID]/)

🖌 [Figma](https://www.figma.com/file/[FILE_ID])


## ⚠️ Avant de commencer :

- [**Docker Desktop pour Mac**](https://docs.docker.com/desktop/install/mac-install/)
- Téléchargez et installer [**Ddev**](https://ddev.readthedocs.io/en/stable/users/install/ddev-installation/)
- Lisez la documentation de [**Ddev**](https://ddev.readthedocs.io/en/stable/)

## 💡Technos utilisées :

- PHP : **8.2**
- MariaDB : **10.4**
- Environnement de développement : **Ddev**
- Stack Back : **Symfony - EasyAdmin - EasyAdminBundle - Twig - Webpack Encore**
- Stack Front : **React - Typescript - TailwindCSS**

## 🏠 Hébergement

**Nom de domaine** : [example.com]

**Hébergement** : [Hebérgeur]

## 🌐 Liens :

- **Local** : [https://symfony-react-project.ddev.site/](https://symfony-react-project.ddev.site/)
- **Préprod** : [https://dev.example.com/](https://dev.example.com/)
- **Prod** : [http://www.example.com/](https://www.example.com/)

## 📦 Installation :

**1.** **Cloner ce dépôt** **:**

```console
git clone git@github.com:agence-adeliom/example.git
```

**2.** **Démarrer le projet** **:**

Dans le fichier .ddev/config.yaml, renommez le nom du projet "symfony-react-project" par le nom de votre projet. C'est ce qui génèrera l'URL de votre projet.

`ddev start`

⚠️ Si vous faites des changements dans le `.ddev/config.yaml`, faites un `ddev restart`

***Installation de FontAwesome*** ***:***

⚠️ Sur ce projet, nous utilisons FontAwesome pour la gestion des icônes.
Pour pouvoir installer le package, remplacer dans le fichier '.npmrc' à la racine du thème 'VOTRE_CLE' par le Package Manager Token à cette url : https://fontawesome.com/account (compte Adeliom dans Bitwarden).
Une fois l'installation passée, merci de retirer la clé du fichier '.npmrc' et de la stocker dans le fichier '.env' de manière à ce qu'elle ne soit pas commit.

Ddev s'occupe de tout :
- création des différents conteneurs docker : appserver, phpmyadmin, node, mailhog
- `ddev auth ssh`
- `ddev composer install`
- `ddev npm install`
- `ddev npm run dev`

**Compilation des assets et autres** **:**
```shell
ddev npm run watch
```

## 📡 Déploiement :
Déploiement via Deployer

Prérequis : avoir ajouté sa clé publique `ed25519` dans la liste des `authorized_keys` sur le serveur. Pour cela se connecter en FTP depuis Infomaniak et se rendre dans le dossier `.ssh`à la racine du serveur.

Ensuite depuis la racine de votre projet en local :

```shell
# Préproduction (branche develop)
ddev deployer deploy staging

# Production (branche main)
ddev deployer deploy production
```


## 🎩 Bonus

<details>

<summary>Afficher les bonus</summary>

### Accéder à la base de données

#### PhpMyAdmin

```shell
ddev phpmyadmin
```

### Accéder à MailPit

```shell
ddev launch --mailpit
```

### Xdebug

```shell
# Activer
ddev xdebug

# Désactiver
ddev xdebug off
```

### Avoir un HTTPS valide en local

```shell
mkcert -install
```

### Faire fonctionner Husky avec SourceTree

```shell
echo 'export PATH="/usr/local/bin:$PATH"' > ~/.huskyrc
```

### Activer Mutagen

Pour améliorer les performances de l'environnement local, il peut être intéressant d'activer Mutagen

Pour l'activer :
- accéder au fichier `.ddev/config.yaml`
- passer la ligne `mutagen_enabled` à `true`
- `ddev restart`

Par défaut, les dossiers des vendors (composer) et des node_modules (npm) sont exclus.

</details>
