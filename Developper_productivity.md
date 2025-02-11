# Intro

presentation de l'atetlier

## a quoi sert la personnalisation de son environnement de travail

- travailler plus vite
- automatiser des taches redondantes
- pouvoir reproduire son environnement rapidement afin de reprendre ses habitudes et son efficacité.

## Sommaire

- les differents shell et leurs personnalisation. (alias, script, themes, zshrc)
- les differents IDEs, raccourcis clavier, snipets, automatisation...
- quelques tools sympa
- les dotfiles.
- optionnel : tmux

## Shell

en tant que developpeur, nous sommes ammené à beaucoup utiliser notre terminal.
l'optimisation de cette partie intrinseque de notre travail nous permet de perdre bien moins de temps au quotidien.

### Les differents shell

	Comme il existe une multitude d'IDEs, il existe aussi differents shell. Le shell va etre l'interpreteur de commande qui tourne sur votre terminal.
	voici les principaux :
	
	<details>
	<summary>1. Sh</summary>
		<ul>
		<li>Tout premier shell.</li>
		<li>Casi pas de personnalisation possible</li>
		</ul>
	</details>
	<details>
	<summary>2. <a href="https://www.gnu.org/software/bash/">Bash</a></summary>
		<ul>
		<li>Shell de base, issue du projet GNU.</li>
		<li>Peu de personnalisation possible.</li>
		</ul>
	</details>
	<details>
	<summary>3. <a href="https://zsh.sourceforge.io/">Zsh</a></summary>
		<ul>
		<li>Liberté casi-absolue sur les personnalisation</li>
		<li>Grosse communauté.</li>
		</ul>
	</details>
	<details>
	<summary>4. <a href="https://fishshell.com/">Fish</a></summary>
		<ul>
		<li>Plus récent.</li>
		<li>Innovant, beaucoup de plugins de base deja installé qui peuvent faciliter l'utilisation.</li>
		<li>Très personnalisable.</li>
		</ul>
	</details>
	<details>
	<summary>5. <a href="https://xon.sh/">Xonsh</a></summary>
		<ul>
		<li>Récent.</li>
		<li>Innovant.</li>
		<li>Supporte le python.</li>
		</ul>
	</details>

Aujourd'hui, nous allons principalement nous focaliser sur zsh, pour son haut degrés de personnalisation. Libre à vous de faire vos recherches concernant les autres shell.

### Oh-my-zsh

le moyen le plus simple et le plus rapide de personnaliser zsh est surement oh-my-zsh. (proposer d'autres alternatives ici)

#### Fonctionnalités principales de oh-my-zsh
1. Theming
2. Gestion de plugins.

les deux vont de paires car certains plugins nous offres des fonctionnalités interressante dans les themes.

#### Comment fonctionne oh-my-zsh

omz va remplacer votre .zshrc (fichier de configuration de zsh) afin de s'installer sur votre shell.
il va aussi se creer un dossier dans votre home nommé .oh-my-zsh, ce sera le dossier qui lui permettra de fonctionner.

Aperçu de l'arborescence de oh-my-zsh :

```
$HOME
└── .oh-my-zsh
│   ├── themes
│   ├── plugins
│   └── themes
└── .zshrc
```

#### Built-ins oh-my-zsh

Apres son installation, oh-my-zsh est deja pre-configurer et vous pouvez l'utiliser directement out of the box.
il arrive notamment avec un tas de themes et de plugins de base. le theme par defaut est robby-russel, mais il y'a des dizaines de themes deja installé
que vous pouvez choisir. [lien vers la liste de themes de base](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)
Pour les plugins, certains plugins sont deja activé, comme git qui fournit les alias comme gcl, gp, ga, gcmsg, ... mais comme pour les themes, pleins d'autres
sont disponibles dès l'installation de oh-my-zsh. [liens vers les plugins de base](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins)

##### Comment changer son theme

Il existe deux methodes : 

###### Modifier le fichier .zshrc :

en modifiant la ligne :

```
ZSH_THEME=$your_theme
```
###### Utiliser la commande omz :

vous pouvez utiliser l'outils omz qui vous permet de changer votre config depuis votre terminal.
voici les commandes concernant les themes :

```sh
omz theme list # Liste les differents themes disponibles sur votre machine
omz theme set $THEME # change votre theme par defaut par le nouveau choisis
omz theme load $THEME # Charge le theme choisis pour la session en cours mais ne change pas le theme par defaut (ideal pour tester un nouveau theme)
```

Vous pouvez aussi set le theme ```random``` comme theme par defaut, et un nouveau theme sera chargé a chaque session (idéal pour tester un peu tout avant de faire son choix)
[plus d'infos sur le random ici](https://github.com/ohmyzsh/ohmyzsh/wiki/Settings#random-theme)

##### Comment manager ses plugins

Comme dit précedemment, oh-my-zsh arrive avec beaucoup de plugins built-ins, mais ils ne sont pas tous activé dans votre config.
Tout comme pour les thèmes, vous avez deux manieres de manager vos plugins :

###### Modifier le fichier .zshrc

le fichier contient un tableau de vos plugins, il suffit de rajouter le nom du nouveau plugin que vous voulez activer :

```
plugins=(plugin1 plugin2 ...)
```

###### Utiliser la commande omz

tout comme les themes, omz vous permet de lister, d'activer et desactiver vos plugins. Voici les commande :

```sh
omz plugin list # Liste les plugins built-ins
omz plugin enable $PLUGIN_NAME # Active un plugin
omz plugin disable $PLUGIN_NAME # Desactive un plugin
```


