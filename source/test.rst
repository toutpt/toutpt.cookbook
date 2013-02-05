Comment écrire des tests
========================

packages::

* plone.app.testing

* niveau: intermédiaire
* audience: développeur

Définitions
-----------

* test unitaire
    Ce test ne dépend QUE du componsant testé. Il n'a pas besoin de base de
    données de serveur ou de n'importe quel autre componsant.

* test d'intégration
    Ce test pose un composant dans le système et on vérifie son bon
    fonctionnement.

* test fonctionnel
    Ce test place le système dans une boite noire et n'utilise que l'interface
    utilisateur pour vérifier le bon fonctionnement de l'ensemble.

* test de performance
    Ce test insère des données et mesure les performances du système sous un
    stress définit (nombre d'utilisateur, quantité de contenu, ...)

* test de sécurité
    Ce test vérifie qu'on ne peut accéder par un moyen détourné à une resource
    dont on est pas censé avoir accès.

Exemples
--------

Voici une série de modules qui ont des tests et que vous trouverez sur github:

* collective.categories
* collective.oembed
* collective.gallery
* collective.sugarcrm

