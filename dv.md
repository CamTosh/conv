DreamVids - Conventions de développement
===

## Code

### Variables
Les variables sont déclarées de la façon suivante:
` [visibility] [type] <name> = [value];`

Exemples: 

`protected string hello = "hello";`

`private $number = 42;`

### Blocs de code
Tous les blocs de code, de n'importe quelle nature, seront déclarés de la façon suivante:

    [type] {
        instruction;
    }

Exemples:

    class Car {
        protected $wheeles = 4;
    }

    public function getNumber() {
        return 42;
    }

## Utilisation de Git & GitHub

### Branches

La branch master doit être une représentation de ce qui se trouve en production.
Par conséquent, tout nouveau travail doit s'effectuter sur une nouvelle branch.

Suivant le type de travail effectué, le nom de la branch doit différer

* Feature
 * feature/nom
* Correction de bug
 * bugfix/nom
* Réorganisation du code
 * rework/nom

Exemples:

    feature/upload
    bugfix/feed-error-500
    rework/comments

### Merging

La fusion des branches avec master doit être effectuée avec précautions et accord du reste de l'equipe.
Avant de fusionner, il faut s'assurer que la totalité des tests passent avec succès afin de conserver la branch master dans un état optimal.