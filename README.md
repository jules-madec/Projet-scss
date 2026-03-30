# DOCUMENTATIONS SCSS


## SOMMAIRES

-Informations
-Méthode BEM
-Préprocesseur, c'est quoi ?
-Installation : NPM & package manager
-Syntaxe SCSS
-Les variables
-Mixins
-Fonctions
-Collections — List & Map
-Boucles — `@for`, `@each`, `@while`
-Multi-fichiers — `@use` & `@forward`
-Architecture 7-1

---
### INFORMATIONS



C'est quoi le SCSS ? :

Le Scss s'est une version améliorer du css qui ajoute des fonctionalite qui rendent le css beaucoup plus pratique et plus propre .

Pourquoi l'utiliser ? : 

On l'utilise car elle rend beaucoup plus propre le code et organiser .On l'utilise aussi car sa nous permet de gagner du temps grace au variable qui est accesible de n'importe quelle fichier ainsi que les mixins et le boucle ou les fonction .

---

### METHODE BEM


Ses quoi la methode BEM ? :

La Méthode BEM est une methode de typage de class pour faciliter est clarifier le code on utilise cette methode elle consite a nommé par exemple une div card est nomme ses enfant avec card est un tirer derriere est le nom de se que on veut mettre comme sa en scss on aura juste a appeler card au debut puis ensuite utiliser & avec le nom qui a apres pour viser se que on veut . 

Exemple :


```html
<div class="card">
    <h1 class ="card_h1">Le h1</h1>
    <p class ="card_p">Le p</p>

</div>

```
```scss
.card{
    background-color:blue
    &_h1{
        font-size:128px
    }
    &_p{
        font-color:red
    }
}

```


---
### PREPROCESSEUR


Il fait quoi le préprocesseur ? : 
Le préprocesseur vas juste compiler le sccs en css pour que le navigateur comprenne est affiche bien 



---
### INSTALLATION NPM & PACKAGE MANAGER


Pour installer NPM : 
- pip install npm

Pour faire un projet avec NPM :
-npm i -D sass 

Le i pour install le -d pour uniquement la version devellopement est sass parceque ses un sass




Puis nous allons ajouter un script dans packgage.json :

'''json
 "scripts": {
    "build": "sass --watch assets/scss:assets/css"
    }

'''


Pour le lancer :
-npm run build


---
### SYNTAXE SCSS


La syntaxe en scss est different on peut imbriquer se que on vise est grace aux bem on peut utiliser aussi  & sur l'exemple on voit que j ai une div avec une class card et que dnas la div j ai un h1 avec 


Exemples :


```html
<div class="card">
    <h1 class ="card_h1">Le h1</h1>
    <p class ="card_p">Le p</p>

</div>

```
```scss
.card{
    background-color:blue
    &_h1{
        font-size:128px
    }
    &_p{
        font-color:red
    }
}
```




---
### LES VARIABLES

Pour les variable nous utilisons un fichier dans abstarct ou nous mettons tous nos variable nous les declarons avec un $ est pour les utiliser nous les declarons dans le fichier avec @use 




```html
<div class="card"></div>
```

```scss
$couleurprincipal:#4da3ff;

.card{
    background-color: $couleurprincipal,
}



```


---
### MIXINS

Les mixins sont des bout de code réutilisable ont les definit dans un fichier _mixins qui est dans le dossier abstact puis comme une variable dans le fichier ou on veut l'utiliser on l'importe avec @use

Exemples :


```html
<div class ="card"></div>
```
```scss
@mixin center {
    display:flex;
    align-items:center;
    justify-content:center;
}
@mixin card($couleur) {
  background-color:$couleur
}
.card{
    @include center;
    @include card(red);
}
```



---
### LES FONCTIONS

Les fonctions sont utiliser pour retourner une valeur avec ou sans parametres



```html
<div class ="card"></div>
```
```scss
@function theme(){
    @return red ;
}
.card {
    background-color: theme;
}
```

```scss
@function theme($value) {
  @return $value;
}

.card {
    background-color: double(red);
}
```

---
### Collections — List & Map

Une liste ses une variables qui contient plusieurs valeurs et une map ses une sort de bibliotheque on assigne a chaque valeur un nom 




```html
<h1 class ="letitre">le titre</h1>
```
List :
```scss
$title:16px,18px,24px ;
.letitre{
    font-size:nth($title ,2)

}
```
Map :
```scss
$text :(
    "xl":1.5rem
    "xm":3rem
    "xs":5rem
)

.letitre{
    font-size:map-get($text,"xl")
    
}
```
---
### Boucles — `@for`, `@each`, `@while`

For repète du code un nombre précis de fois .

Each parcourt une liste ou un groupe de valeurs.


Répete du code tant qu’une condition est vraie.

for : 

```scss
@for $i from 1 through 3 {
  .box-#{$i} {
    width: 10px * $i;
  }
}
.box-1 { width: 10px; }
.box-2 { width: 20px; }
.box-3 { width: 30px; }
```
each :
```scss
$colors: red, blue;

@each $c in $colors {
  .text-#{$c} {
    color: $c;
  }
}
.text-red { color: red; }
.text-blue { color: blue; }
```
while :
```scss
$i: 1;

@while $i <= 2 {
  .w-#{$i} {
    width: 20px;
  }
  $i: $i + 1;
}
.w-1 { width: 20px; }
.w-2 { width: 20px; }
```

---
### Multi-fichiers — `@use` & `@forward`

Importer un fichier :

```scss
@use 'variables';
```
Permet de regrouper des fichiers :
```scss
@forward 'variables';
```
---

### ARCHITECHTURE
scss/

├─ abstracts/

├─ base/

├─ components/

├─ layout/

├─ pages/

├─ themes/

└─ main.scss














