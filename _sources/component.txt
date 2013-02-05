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

Théorie
-------

La théorie des composants s'inspire du monde de l'électronique. Un composant
défini comme entrée X et fourni comme sortie Y. La programmation par componsant
est donc un sous ensemble de la programmation orientée objet.

Pratique
--------

Le componsant est donc ni plus ni moins qu'un objet python. Celui ci peux donc
hériter de classes existantes ou non.

Dans Zope il y a un registre de componsant globale au près du quel vous devez
enregistrer votre componsant. Pour ce faire vous devez utiliser un fichier 
*zcml*. Il faut voir ce registre comme une grosse structure de donnée en mémoire
à qui vous pouvez dire::

  je veux le componsant qui fourni l'interface IVoiture en sortie et qui prend
  l'instance 'conducteur'.

Le registre va donc regarder quels sont les interfaces implémentées par les
instance en entrée et fournir une instance d'un composant en sortie.


Exemple: utility
----------------

Cet exemple est issue du module collective.sugarcrm

fichier password.py:

.. code-block:: python

    from hashlib import md5
    from zope import interface
    
    class IPasswordEncryption(interface.Interface):
        """Utility to crypt your password before use it with the WebService"""
    
        def crypt(password):
            """Return the encrypted password for the current service"""
    
    class Password(object):
        """Password default encryption for sugarcrm"""
        interface.implements(IPasswordEncryption)
    
        def crypt(self, password):
            m = md5()
            m.update(password)
            return m.hexdigest()

fichier configure.zcml:

.. code-block:: xml

    <utility
        factory=".password.Password"
        provides=".interfaces.IPasswordEncryption"
        />

utilisation:

.. code-block:: python

    password = component.getUtility(interfaces.IPasswordEncryption)
    crypted = password.crypt('mon mot de passe')
