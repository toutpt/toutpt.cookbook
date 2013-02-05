Tout sur les profiles d'installation
====================================

Problème: mon module n'installe pas tout ce qu'il faut j'ai beau modifier les
fichiers xml rien n'y fait.

Définitions
-----------

* profile (profil):
    Il s'agit d'une configuration précise des paramètres persistents. Un
    profile qui est appliqué c'est une configuration qui est modifiée.
    Un profile dispose d'une version et de dépendances qui sont définit par le
    fichier metadata.xml. Par convention vous trouverez les profiles d'un
    module dans le dossier profiles et le profile par défaut s'appel default.

* (import step):
    Une import step est une étape qui est responsable de la gestion d'un
    fichier XML comme par exemple registry.xml. Le code des steps est par
    convention dans un fichier exportimport.py

* (export step):
    Une export step est une étape dans le processus d'export qui est responsable
    de sortir un fichier XML détaillant la configuration actuelle.

* upgrade step:
    Une upgrade step est une étape qui définit le passage d'une version d'un
    profile à une autre. Par convention les step sont dans le fichier upgrades.py


