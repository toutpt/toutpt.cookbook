Comment écrire des componsants zope
===================================

packages:

* zope.interface
* zope.component

* niveau: débutant
* audience: développeur

Définitions
-----------

* Composant (component)
    Un objet qui définit une interface en sortie et qui prend des objets en
    entrée fournissant euh même des interfaces définies

* Utilitaire (utility)
    C'est un composant qui ne prend aucun objet en entré.

* Adaptateur (adapter)
    C'est un componsant qui ne prend qu'un seul objet en entré.

* Adaptateur mutliple (multi adapter)
    C'est un componsant qui prend plusieurs objets en entré.

Exemples
--------

Todo ajouter des exemples pour chaque type de componsant

Théorie
-------

La théorie des composants s'inspire du monde de l'électronique. Un composant
défini comme entrée X et fourni comme sortie Y. La programmation par componsant
est donc un sous ensemble de la programmation orientée objet.
