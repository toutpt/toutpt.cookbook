Installer les outils
====================

Problème: vous souhaitez développer un module pour le CMS Plone.

* prérequis 1: connaissance de base en unix/linux
    Vous devez être capable d'installer Python avec les sources ainsi que de
    comprendre pourquoi une installe ne compile pas.

* prérequis 2: Python
    Vous savez coder avec Python

Plone
-----

il y a deux manières d'installer Plone:

Vous pouvez télécharger et installer Plone à l'aide d'une archive
à cette adresse: http://plone.org/products/plone. C'est la méthode si vous
souhaitez juste essayer Plone.

Pour les développeurs: Vous devez mettre à disposition un python 2.7 
avec les sources et utiliser la mécanique de déploiement buildout.

Dans la pratique un développeur fourni un buildout à la racine de ses modules
qui permet d'installer un Plone vierge avec juste le module en question via
les commandes suivantes::

    python bootstrap.py
    bin/buildout

Vous pouvez donc passer à la suite sans avoir installé Plone.

Configurer buildout
-------------------

Vous devez configurer buildout pour ne pas installer Plone à chaque fois mais
avoir un dépot central des packages sur votre machine. Pour celà vous pouvez
récupérer dans le répo git ci après le dossier .buildout et le mettre dans le
home de votre ordinateur

    cd
    git clone https://github.com/plone/plone.dotfiles
    cp -R plone.dotfiles/.buildout .
    vim .buildout/default.cfg

Vous devez en effet éditer les chemins pour mettre les chemins absolus de votre
machine.

Les outils
----------

La bonne pratique c'est d'avoir sa boite à outil dans un dossier séparé et non
pas demandé à chaque petit buildout d'installer tous les outils du monde.

Vous avez pour cela un buildout disponible::

    cd
    git clone http://github.com/toutpt/mypythontools plonetools
    cd plonetools
    python bootstrap.py
    bin/buildout
    cd

Vous avez la dedans:

* un outil de traduction
* un générateur de module
* un générateur de thème

Générer un module
-----------------

Vous avez maintenant de quoi générer un module, ce que nous allons tout de
suite faire::

    cd
    ./plonetools/bin/zopeskel toutpt_collective collective.monmodule
    cd collective.monmondule
    python boostrap.py
    bin/buildout

La première fois c'est long car Plone est composé de nombreux packages qui sont
téléchargés à la suite les un des autres.

Vous avez maintenant un Plone mis à disposition, vous n'avez plus qu'à démarrer
le serveur Zope

    bin/instance fg

