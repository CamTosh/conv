DreamVids - Conventions de développement
===

##Développement front-end

L'indentation se fait en tabulation de taille 4.

###JavaScript

####Fichiers

Tout les fichiers scripts doivent comporter un bloc de commentaire en haut de ce dernier.

```js
/**
 *	path/to/file.js
 *
 *	Description du script.
 */
```

Le nommage des fichiers doit se faire en anglais, en minuscule avec des séparations par tirets, exemple `file-name.js`.

####Syntaxe

On insère toujours un espace après une virgule `,` et on insère un espace avant les ouvertures d'accolade `{`.
Un insère une nouvelle ligne après une ouverture d'accolade et avant sa fermeture. On insère également une nouvelle ligne entre les blocs de conditions.

Le but étant d'aérer le code, soyez créatifs ! Même si cela peut "prendre de la place", cette méthode permet de mieux visualiser le code.

```js
// good
function action(propertie, variable) {

	if (propertie === "string") {

		return true;

	}

	else {

		return false;

	}

}

// bad
function action(propertie,variable){
	if(propertie==="string"){
		return true;
	} else{ return false; }
}
```

####Variables

Les variables doivent être nommées en anglais en utilisant la syntaxe `camelCase`.
Il est obligatoire d'utiliser l'argument `var` pour déclarer une variable.


```js
// good
var currentTime = 0;

// bad
var currenttime = 0;
var current_time = 0;
var ceTempsCi = 0;
currentTime = 0;
```

####Chaînes de caractère

On utilise en priorité des `double quotes` pour entourer les chaînes de caractères .

```js
// good
var foo = "bar";

// bad
var foo = 'bar';
```

####Fonctions

On utilise toujours la même syntaxe pour déclarer une fonction :

```js
function name(propertie, something) {

	/* Code */

}

something.action = function(propertie, something) {

	/* Code */

};

// Fonction immediatement invoquée
function(bind) {
	
	return function() {
	
		/* Code */
	
	};
	
}(bind);
```

####Boucles

Pour réaliser une boucle dans un tableau, on utilise toujours cette syntaxe :

```js
for (var i = 0, length = array.length; i < length; i ++) {

	/* array[i] */
	
}
```

Le nom des variables peut différer si une boucle se situe à l’intérieur d'une autre.

```js
for (var i = 0, length = array.length; i < length; i ++) {

	for (var j = 0, innerLength = array[i].length; j < innerLength; j ++) {

		/* array[i][j] */
	
	}
	
}
```

###Sass

####Fichiers

Tout les fichiers de style doivent comporter un bloc de commentaire en haut de ce dernier.

```scss
/**
 *	path/to/file.scss
 *
 *	Description du script.
 */
```

Le nommage des fichiers doit se faire en anglais, en minuscule avec des séparations par tirets, exemple `file-name.scss`.

####Syntaxe

On insère toujours un espace avant les ouvertures d'accolade `{`.
On insère une nouvelle ligne après une ouverture d'accolade et avant sa fermeture.

La gestion de l'espace est la même que pour les fichiers scripts.

```scss
// good
.button {

	display: block;
	margin: 10px;

}

// bad
.button{
	display:block;
	margin:10px;
}
```

####Classes

Le nommage des classes css doit suivre la convention de notation BEM, avec `component`, `component__element`, et `component--modifier`.

```scss
// Exemple

.button { /* Style */ }

.button--red {

	background: red;
	
}

.button__text { /* Style */ }
```
```html
<div class="button button--red">
	<div class="button__text">Click me!</div>
</div>
```

####Propriétés

Les propriétés possèdent un ordre spécifique à leur utilité.

 - position
 - display
 - style
 - includes & extends

```scss
// Exemple

.button {

	position: relative;
	top: 16px;
	right: 8px;

	display: block;
	margin: 10px;
	padding: 10px;

	background: red;
	color: yellow;
	border: 1px solid green;

	@include border-radius(5px);

}
```

####Variables

Les variables doivent être nommées en anglais, en minuscules avec séparations par tirets.
Les variables spécifique à un type d'élément peuvent être définies au début du fichier de ce component. Les autres variables qui peuvent êtres utilisées par tout les components doivent être définies dans un des trois fichiers du dossier `variables` : `colors.scss`, `sizes.scss` ou `other.scss`.