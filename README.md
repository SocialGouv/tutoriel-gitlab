# Tutoriel GitLab ![Work in progress](http://www.repostatus.org/badges/latest/wip.svg)

Ce guide collaboratif à l'ambition de vous donner les bases essentielles pour bien démarrer sur [GitLab](http://gitlab.org).

[GitLab](http://gitlab.org) peut être utilisé en tant que [SAAS](https://fr.wikipedia.org/wiki/Logiciel_en_tant_que_service), ou être installé sur votre propre instance privée.

> NB: les traductions FR des interfaces ne sont pas toujours complètes.

## Sommaire

 - [Qu'est-ce que c'est, à quoi ça sert ?](#quest-ce-que-cest-%C3%A0-quoi-%C3%A7a-sert-)
 - [Comment fonctionne GIT](#comment-fonctionne-git)
 - [Sécurité](#sécurité)
 - [Inscription GitLab](#inscription)
 - [Créer un projet](#créer-un-projet)
 - [Fourcher (forker) un projet](#fourcher-forker-un-projet)
 - [Gestion des fichiers](#gestion-des-fichiers)
 - [Demandes de fusion](#demandes-de-fusion)
 - [Le format Markdown](#am%C3%A9liorer-ses-textes-avec-le-format-markdown)
 - [Gestion des issues](#les-issues)
 - [GitLab : Mirroring avec GitHub](#gitlab--mirroring-avec-github)
 - [FAQ](#faq)
 - [Liens](#liens)
 - [Glossaire](#glossaire)

## Qu'est-ce que c'est, à quoi ça sert ?

**GIT** est un système de gestion de versions, qui permet de stocker de manière optimisée et sécurisée des fichiers **et** toutes leurs modifications dans le temps.

**GIT** est décentralisé, et permet à de multiples personnes de travailler ensemble sur le même projet, puis d'intégrer harmonieusement les travaux de chacun.

C'est un outil bas niveau (ligne de commande), mais on peut l'utiliser via des logiciels comme GitKraken par exemple.

Des sites webs comme GitHub ou GitLab (qui sont des "forges logicielles"), ajoutent à GIT des fonctionnalités telles que la gestion des "tickets" (issues), les releases, la documentation, l'intégration continue ou encore le déploiement automatisé, qui facilitent la collaboration, et en font une composante centrale pour atteindre l'agilité et les pratiques **DevOps**.

**GitHub**, c'est le site web (SAAS) qui a démocratisé l'usage de GIT, en lui ajoutant une surcouche web minimaliste mais permettant une collaboration facilitée. Il est devenu **LA référence** des développeurs pour tous les projets open-source populaires. Il fédère plus de 25 millions d'utilisateurs dans le monde qui collaborent tous les jours sur cette plateforme. https://fr.wikipedia.org/wiki/GitHub

**GitLab**, c'est une alternative open-source, idéale pour des usages privés ou plus avancés, et qui propose beaucoup plus de fonctionnalités. Le projet est financé par de nombreuses entreprises (dont Google Ventures) et est proposé en version CE : Community edition (gratuite) ou Entreprise pour bénéficier de fonctionnalité très avancées et de support. https://fr.wikipedia.org/wiki/GitLab_CE

Un [glossaire](#glossaire) est disponible à la fin de ce document


## Comment fonctionne GIT

GIT maintient dans votre projet des fichiers d'index qui stockent chaque modification de fichier, ainsi qu'un lien vers la version précédente.

Ainsi, à chaque "commit" (modification de fichier(s)), vous enregistrez les nouvelles modification dans l'index.

Et vous pouvez revenir en arrière à tout moment, ou créer des "branches" qui vous permettront de travailler en parallèle sur une nouvelle version du fichier.

[![https://www.atlassian.com/git/tutorials/using-branches/git-merge](./images/git-branches.png)](https://www.atlassian.com/git/tutorials/using-branches/git-merge)

Concrètement, à la racine de votre projet, git maintient un dossier `.git` qui contient les indexes et le fichier de config.

## Sécurité

Les autorisations d'accès aux projets sont gérées par les propriétaires des projets dans GitLab.

Vous ne devez pas mettre de mot passe ou donnée sensible dans les projets.

## Inscription

Vous êtes autonome pour créer un compte sur la plateforme.

Merci de respecter la convention `prenom.nom` lors de votre enregistrement.

![register](./images/register.png)

Une fois votre compte créé, vous pouvez créer des projets comme bon vous semble dans votre espace personnel.

Le nommage des projets par groupe doivent respecter des conventions de nommage.

## Créer un projet

Créer un projet, c'est créer un espace public ou privé ou vous pouvez versionner des fichiers et collaborer.

![creer depuis menu](./images/create-project1.png)

![creer depuis accueil](./images/create-project2.png)

Lorsque vous créez un nouveau projet, il peut résider :

 - soit dans votre espace personnel : https://[URL]/prenom.nom/nom-du-projet
 - soit dans un groupe existant : https://[URL]/groupe/nom-du-projet

![options du projet](./images/create-project3.png)

Plusieurs options de visibilité sont disponibles :

Visibilité  | Invité
------------|-------
Privé       | Vous serez le seul à pouvoir accéder au projet et à donner des permissions à l'unité
Interne     | Seuls les utilisateurs authentifiés peuvent voir le projet
Public      | N'importe qui, même non authentifié peut voir le projet

Une fois le projet crée, vous pouvez commencer à l'utiliser.

Si le projet est privé, vous pouvez inviter des utilisateurs à collaborer.

![options membres](./images/project-members-menu.png)

Vous pouvez inviter des utilisateurs individuellement, ou par groupe.

Role        | Permissions
------------|---------------
Guest       | Lire et commenter les issues
Reporter    | Gérer les issues, voir le code
Developer   | Modifier les fichiers, issues
Master      | Administration du projet

Cf [permissions](#gitlab-les-permissions)

![options membres](./images/project-members.png)

### Options du projet

Un certain nombre d'options permettent de personnaliser le projet

![options du projet](./images/project-options.png)

Parmi les options réglables, vous pouvez :

 - personnaliser le logo, description, tags du projet
 - régler les permissions d'accès
 - activer/désactiver les issues/pipelines/wikis/snippets si vous n'en avez pas besoin (cella allège l'affichage)

### Accueil du projet

Cette page permet d'avoir toutes les informations sur le projet.

Le fichier `README.md` est automatiqueemnt affiché et doit permettre de comprendre les tenants et les aboutissants du projet, ainsi que les moyens pour installer le projet ou collaborer.

Si le projet vous intéresse, mettez-le en favori pour le retrouver facilement sur la page d'accueil ou dans le menu"

![projet-bookmark](./images/project-bookmark.png)

Exemple de page d'accueil d'un projet GitLab :

![Accueil du projet](./images/project-home.png)

L'URL présentée en haut du projet, qui peut-être de type HTTPS ou SSH permet de pouvoir clôner le projet, pour le rappatrier sur sa machine par exemple.

![URL du projet](./images/project-url.png)


## Fourcher (forker) un projet

Pour contribuer à un projet sur lequel nous n'avons pas les droits en écriture, il est d'usage de `fourcher` le projet, d'apporter les modifications (corrections ou améliorations) dans votre propre copie du projet, puis d'envoyer cette contribution en tant que `merge request` au projet original (qu'on appelle `upstream`).

![Fourcher un projet](./images/project-fork.png)

Vous pouvez `fourcher` un projet depuis la page web du projet, c.a.d. le copier, soit dans votre espace personnel, soit dans un groupe pour lequel vous avez les permissions suffisantes.

Une fois fourché, vous êtes en possession d'une copie du projet sur laquelle vous pouvez travailler indépendamment puis éventuellement soumettre des contributions utiles au projet d'origine (`upstream`)

## Gestion des fichiers

Les fichiers d'un repository peuvent être modifiés de multiples façons :

 - Via le **site web** : facile et rapide
 - Via un **logiciel dédié** : permet de travailler sur son poste indépendemmant avant d'envoyer les changements
 - Via le **CLI GIT** : permet de comprendre le fonctionnement de GIT et de travailler très précisément

Les 3 approches sont décrites ci-dessous.

### Via l'interface web

GitLab propose une interface web riche d'où il est possible de faire beaucoup de choses :)

Pour créer, envoyer un fichier ou un dossier :

![projet-ajouter-fichier](./images/project-add-file.png)

Pour modifier un fichier, ouvrez le fichier en cliquant sur son nom, puis cliquez sur "Edit"

![projet-editer-fichier](./images/project-edit-file.png)

Vous accédez alors à un éditeur de texte qui permet de modifier le fichier.

Une fois le fichier envoyé ou modifié, vous devez le "commit", c'est à dire sauvegarder vos changements et les décrire brièvement.

ex: "doc: mise à jour des informations d'installation"

> 💡 Des [conventions de commit](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#-git-commit-guidelines) permettent de standardiser les messages et de générer des changelogs.


## GitLab : Via un logiciel UI

On peut également travailler sur les fichiers directement sur son ordinateur, sans passer par l'interface GitLab.

Pour cela on peut utiliser l'un des nombreux clients GIT du marché. Le plus "simple" est [GitHub for desktop](https://desktop.github.com/)

 - On va d'abord cloner le projet (copier en local).
 - Puis faire les modifications en local
 - Faire un commit
 - Envoyer le code sur GitLab (push)

## GitLab : via le CLI GIT

> La ligne de commande GIT est cryptique, mais il y a peu de commandes à connaitre; les connaitre vous permettra de mieux comprendre le fonctionnement de GIT pour mieux en tirer profit.

> 💡 Apprenez le CLI en 5 minutes avec [try.github.io](http://try.github.io)

### Clé SSH

Pour utiliser le CLI, le plus simple est d'utiliser une clé SSH que vous associer à votre compte GitLab. Ceci permet de ne pas avoir à utiliser les mots de pass via le CLI.

 - générez la clé sur votre poste
   - windows : avec [putty](https://support.google.com/youtube/answer/3071034?hl=fr)
   - mac/linux : `ssh-keygen -t ecdsa -b 256`
     
 - ajoutez la clé **publique** dans votre profil GitLab


### Clone/Modif de repos

Les mêmes opération via le CLI (ligne de commandes) :

 - cloner un projet `git clone git@gitlab..aaa.bbb.ccc:/prenom.nom/faq-generale.git`
 - Ajouter les fichiers pour le commit `git add question-1.md question-2.md`
 - Sauvegarder les modifications : `git commit -m 'ajout de questions'`
 - Envoyer sur le serveur GitLab : `git push`

## Demandes de fusion

Lorsque vous modifiez des fichiers sur un projet qui ne vous appartient pas, vous pouvez soumettre vos changements pour validation au propiétaire du projet.

Ceci permet de faire une revue, à l'issue de laquelle le propriétaire pourra directement intégrer vos changements dans le projet.

## Améliorer ses textes avec le format markdown

Le format markdown permet d'enrichir facilement du texte brut. Dans GitLab, on peut écrire du markdown a peu près partout : fichiers `.md`, commentaires, issues...

Ce format est exploitable par de nombreux outils, qui permettent par exemple de générer des sites web.

Documentation complète ici : https://fr.wikipedia.org/wiki/Markdown

Quelques outils pratiques :

 - Un éditeur en ligne : [dillinger.io](http://dillinger.io)
 - un tutoriel interactif : https://www.markdowntutorial.com/
 - Helper pour générer des tableaux : https://www.tablesgenerator.com/markdown_tables
 - Format `mermaid` pour générer des schémas : https://gitlab.com/gitlab-org/gitlab-ce/issues/3711

## Les issues

Le système d'issues de GitLab est avancé et puissant !

Vous pouvez créez des catégories (tags), assigner les tâches, les estimer, gérer des roadmaps, ajouter des fichiers, commenter, recevoir des notifications, etc... un lieu idéal pour centraliser les discussions autour d'un projet et favoriser la collaboration transparente.

Pour accéder aux issues du projet :

![issues-menu](./images/issues-menu.png)

Vous accédez alors à la liste des issues du projet

![issues-list](./images/issues-list.png)

Pour créer une issue :

![issues-new](./images/issues-new.png)

Créer une bonne issue est essentiel pour sa résolution. Chaque issue doit être explicite, avec **un cas reproductible** en cas de remontée de bug. Vous pouvez avoir quelques pistes pour [rédiger un bon rapport de bug ici](http://blogtorop.fr/comment-faire-un-bon-rapport-de-bug/).

### Agile

Les issues peuvent être organisées dans des "boards" type "kanban". Vous pouvez créer vos propres boards pour organiser vos priorités.

![issues-boards](./images/issues-boards.png)

Les issues peuvent être groupés par "milestones" (sprints). Ceci permet de grouper des tâches pour en suivre la complétion.

![issues-milestones](./images/issues-milestones.png)

## GitLab : Les permissions

Les utilisateurs ont des permissions différentes selon le niveau d'accès qu'ils ont dans un groupe ou un projet particulier.

Si un utilisateur est à la fois dans le projet d'un groupe et le projet lui-même, le niveau d'autorisation le plus élevé est utilisé.

Quand on créé un projet, nous en sommes le "Owner", et accordons des permissions à d'autres membres si nécéssaire.


Permission                  | Invité| Reporter | Developer | Master | Owner
----------------------------|:-----:|:--------:|:---------:|:------:|:------:
Issues                      |   ✔   |     ✔    |     ✔     |   ✔    |   ✔   |
Gérer les issues            |   ⨯   |     ✔    |     ✔     |   ✔    |   ✔   |
Effacer une issue           |   ⨯   |     ⨯    |     ⨯     |   ⨯    |   ✔   |
Lire le wiki                |   ✔   |     ✔    |     ✔     |   ✔    |   ✔   |
Editer le wiki              |   ⨯   |     ⨯    |     ✔     |   ✔    |   ✔   |
Commenter                   |   ✔   |     ✔    |     ✔     |   ✔    |   ✔   |
Edit un commentaire         |   ⨯   |     ⨯    |     ⨯     |   ✔    |   ✔   |
Lire le code                |   ⨯   |     ✔    |     ✔     |   ✔    |   ✔   |
Contribuer (merge request)  |   ⨯   |     ⨯    |     ✔     |   ✔    |   ✔   |
git push                    |   ⨯   |     ⨯    |     ✔     |   ✔    |   ✔   |
Gérer l'équipe projet       |   ⨯   |     ⨯    |     ⨯     |   ✔    |   ✔   |
Configurer les pages projet |   ⨯   |     ⨯    |     ⨯     |   ✔    |   ✔   |
Créer un projet dans groupe |   ⨯   |     ⨯    |     ⨯     |   ✔    |   ✔   |
Transférer un projet        |   ⨯   |     ⨯    |     ⨯     |   ⨯    |   ✔   |
Effacer un project          |   ⨯   |     ⨯    |     ⨯     |   ⨯    |   ✔   |
Voir les jobs               |   ✔   |     ✔    |     ✔     |   ✔    |   ✔   |
Configurer les hooks        |   ⨯   |     ⨯    |     ⨯     |   ✔    |   ✔   |
Voir les environments       |   ⨯   |     ✔    |     ✔     |   ✔    |   ✔   |
Créer un environment        |   ⨯   |     ⨯    |     ✔     |   ✔    |   ✔   |

cf [documentation officielle](https://docs.gitlab.com/ee/user/permissions.html#project-members-permissions)


## GitLab : Gestion de projet (boards)

[todo]

## GitLab : Publier du contenu avec GitLab pages

[todo]

## GitLab : Mirroring avec GitHub
Gitlab offre la synchronisation en PUSH vers Github à tous les utilisateurs tandis que la synchronisation en GET est réservée aux comptes Gitlab PREMIUM (payant).

1.Clonage d'un repo Github dans Gitlab

Gitlab propose de créer un repo en créant un clône d'un repo pré-existant sur un autre service via "Importer un projet". Il suffit de fournir l'URL du repo Github.

![Capture de la page de proposition des modalités de création de repo Gitlab](./images/gitlab-clonage1.png "Clonage d'un repo pré-existant")

L'interface demande ensuite de remplir des champs : 
- le nom d'utilisateur correspond au nom d'utilisateur du repo distant Github
- le mot de passe correspond à un token d'accès personnel que nous devons générer depuis https://github.com/settings/tokens pour autoriser Gitlab à tirer depuis notre compte Github
- cocher la case "Dépôt miroir"

![Capture des Champs demandés par Gitlab pour autoriser le clonage du projet](./images/gitlab-clonage2.png "Champs demandés par Gitlab pour autoriser le clonage du projet")

2.Pousser le repo Gitlab vers Github

La poussée des modifications vers le dépôt Github comprend Les branches, les étiquettes et les commits.

Pour cela il faut se rendre dans le repo Gitlab -> Paramètres -> Dépôt -> Dépôts miroirs.
Il faut de nouveau coller l'url du dépôt distant Github et placer le nom d'utilisateur Github. Le champ "mot de passe" correspond au token généré précédemment sur Github.

![Capture des champs requis pour synchroniser](./images/gitlab-synchronisation.png "Champs requis pour synchroniser")

N'importe quel commit effectué sera poussé depuis Gitlab vers Github.

## GitLab : Intégration continue

[todo]


## FAQ

### Clé SSH

[todo]

## Liens

 - [L'art de faire des commits atomiques](http://adopteungit.fr/methodologie/2017/04/26/commits-atomiques-la-bonne-approche.html)
 - [L'art de faire des issues efficaces](https://www.lesintegristes.net/2011/10/19/rediger-un-rapport-de-bugs-ca-na-pas-lair-pas-mais-cest-du-boulot/)

## Glossaire
 - **intégration continue** : pratique qui consiste à vérifier chaque modification du code source pour prévenir les régressions.  Le principal but de cette pratique est de détecter les problèmes d'intégration au plus tôt lors du développement. De plus, elle permet d'automatiser l'exécution des suites de tests et de voir l'évolution du développement du logiciel.
 - **devops** : mouvement visant à l'alignement de l'ensemble des équipes du système d'information sur un objectif commun, à commencer par les équipes de dev ou dev engineers chargés de faire évoluer le système d'information et les ops ou ops engineers responsables des infrastructures.
 - **commit** :  Fait d'enregistrer dans un outil de gestion de versions une nouvelle version d'un ensemble de fichiers.
 - **release** : version fixée d'une réalisation
 - **issue** : Un ticket qui permet de définir une feature ou un bug.
 - **repository** : Un projet au sens GIT
 - **origin** : GIT étant décentralisé, `origin` est le nom conventionnel du serveur par défaut
 - **upstream** : Lorsque l'on copie (fork) un projet, `upstream` représente le repository d'origine par convention
 - **fourcher/forker** : copier intégralement un repository
