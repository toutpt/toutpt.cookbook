Installer les outils
====================

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

Les outils
----------

La bonne pratique c'est d'avoir sa boite à outil dans un dossier séparé et non
pas demandé à chaque petit buildout d'installer tous les outils du monde.

Vous avez pour cela un buildout disponible ici: http://github.com/toutpt/mypythontools

    git clone http://github.com/toutpt/mypythontools plonetools
    cd plonetools
    python bootstrap.py
    bin/buildout

Vous avez la dedans:

* un outil de traduction
* un générateur de module
* un générateur de thème
