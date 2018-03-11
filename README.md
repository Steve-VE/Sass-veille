# Sass, SCSS, ...
## Qu'est-ce ?
Le *Sass* (pour *"Syntactically  Awesome  Stylesheets"*) est un langage de génération de feuilles CSS (un préprocesseur CSS). Cela permet d'écrire plus rapidement du CSS, d'organiser et de maintenir plus simplement nos feuilles de style.
Sass hérite de certains concepts propre à la programmation, comme les variables, l'utilisation des opérations mathématique ou la possibilité d'utiliser des boucles ou des fonctions.
Il est possible aussi d'utiliser les mots clés ```@extend ``` pour réutiliser les règles de style d'une autre classe, ```@import``` pour importer un fichier Sass (ce qui permet de diviser son travail en plusieurs catégorie) et ```@mixin``` pour attribuer d'un coup plusieurs règles de style, et même de lui passer des paramètres un peu à la manière d'une fonction ([guide sur le Sass](https://sass-lang.com/guide)).

Le [Sass](https://sass-lang.com/) a été conçu en [Ruby](https://www.ruby-lang.org/fr/), vous aurez donc besoin de l'installer s'il n'est pas présent sur votre machine. De même pour le SCSS qui découle simplement du Sass, mais qui utilise une syntaxe plus proche du CSS classique, ce qui rend le code plus lisible et moins sujet à erreur que le Sass (mais qui en contrepartie est un peu plus long à écrire).
Quant au [LESS](http://lesscss.org/), il est compilé en *Javascript* et ne nécessite donc pas l'installation de *Ruby*.

Actuellement, les navigateurs internet n'interprètent pas le Sass. Il faut obligatoirement compiler son code pour obtenir un fichier CSS afin de pouvoir l'utiliser. Il y a plusieurs façon de compiler son code, que ce soit via le terminal, à l'aide d'un logiciel prévu à cet effet (exemple: [Koala](http://koala-app.com/)) ou directement dans son éditeur de code préféré à l'aide d'un "*watcher*" (exemple: [Live Sass Compiler](https://marketplace.visualstudio.com/items?itemName=ritwickdey.live-sass) pour **Visual Studio Code**, ou [compile-watch](https://atom.io/packages/compile-watch) pour **Atom**).

## Quel préprocesseur choisir ?
La principale différence se trouve dans leur syntaxe, car Sass, LESS ou SCSS permettent la même chose.
### Sass :
```SASS
$main_color: #3bbfce
$margin: 16px

p
  margin: $margin
  padding: $margin / 2
  border-color: $main_color
  color: darken($main_color, 10%)
  a
    text-decoration: none
    &:hover
      color: lighten($main_color, 20%)
```
Le Sass s’embarrasse du moins de chose possible... Donc ici, pas d'accolades, pas de point virgule, ce sont les tabulations et les retours à la ligne qui permettent de structurer notre code.
**Avantage :** Rapide et minimaliste
**Inconvénient :** Facilement source d'erreur

### SCSS :
```SCSS
$main_color: #3bbfce;
$margin: 16px;

p {
  margin: $margin;
  padding: $margin / 2;
  border-color: $main_color;
  color: darken($main_color, 10%);

  a {
    text-decoration: none;

    &:hover {
      color: lighten($main_color, 20%);
    }
  }
}
```
Le SCSS reste plus proche du CSS classique tout en incluant les possibilités offerte par le Sass. 
**Avantage :** Plus facile à lire car similaire à du CSS classique
**Inconvénient :** Moins synthétique que le Sass

### LESS : 
```LESS
@main_color: #3bbfce;
@margin: 16px;

p {
  margin: @margin;
  padding: @margin / 2;
  border-color: @main_color;
  color: darken(@main_color, 10%);

  a {
    text-decoration: none;

    &:hover {
      color: lighten(@main_color, 20%);
    }
  }
}
```
Le LESS est sensiblement le même que le SCSS (notez les @ à la place du $ dans le nom des variables). Sa principale différence étant qu'il utilise Javascript et non Ruby.

### Une fois compilé...
Dans les trois cas, une fois le code compilé, on obtiendra la même chose en **CSS** : 
```CSS
p {
  margin: 16px;
  padding: 8px;
  border-color: #3bbfce;
  color: #2b9eab;
}
p a {
  text-decoration: none;
}
p a:hover {
  color: #8ddae2;
}
```
Vu que le résultat et les possibilités sont les mêmes, choissisez celui avec la syntaxe qui vous plait le plus.
Ces trois-ci sont les plus courant mais il y en a encore d'autre. Cependant, plus un "langage" est populaire, et plus facilement vous trouverez des ressources, des tutos ou de l'aide.

## Où tester sans se prendre la tête ?
[CodePen](https://codepen.io/pen/) permet d'essayer le [Sass](https://sass-lang.com/), le *SCSS*, le [LESS](http://lesscss.org/), [Stylus](http://stylus-lang.com) et [PostCSS](http://postcss.org). Pour cela, il suffit de cliquer sur le petit rouage (*settings*) dans la fenêtre CSS et de choisir un*CSS Preprocessor*.
Il existe aussi des plateformes en ligne pour écrire et compiler son code (exemple : [SassMeister](https://www.sassmeister.com/) ou [WinLess](http://winless.org/online-less-compiler)).

## Des tutos pour débuter ?
Il existe énormément de tutoriaux et d'articles parlant du Sass et de ces dérivés/alternatives. 
Voici quelques vidéos en français : 
- [CSS boosteé aux stéroïdes avec Sass et SCSS](https://www.youtube.com/watch?v=ydDYdTJILpY) : Vidéo de présentation et d'initiation.
- [Tutorial SASS](https://www.youtube.com/playlist?list=PL0TnHYy48T2zAl4x8I_wFLq36Aqt34Art) : Série de vidéos pour apprendre le Sass.
- [À la découverte de SASS](https://www.youtube.com/watch?v=PxJoEMAUEuk) : (très longue) vidéo de découverte et d'explication du Sass/SCSS.
