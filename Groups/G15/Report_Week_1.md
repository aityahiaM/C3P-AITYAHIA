## Nom : AIT YAHIA 
## Prénom : Maya 
 

# 1 - Apprendre les collections dans pharo et leurs itérateurs :

## Une collection : 

est un ensemble d'éléments regroupés sous une meme structure.
Les collections sont utilisées pour stocker et manipuler des ensembles de données.

## Les types de collections : 

- OrderedCollection (dynamically growing) : une collection ou les éléments sont ordonnés 
- Set(no duplicates) : une collection sans doublons 
- Dictionary (key-based, aka, maps )  : une collection d'éléments organisés par paires clé/valeur 
- Array(fixed size, direct access) : une collection d'éléments de taille fixe 

## L'itération sur les collections : 

do: exécute un bloc de code pour chaque élément de la collection.
```bash
Exemple : 
n := 0.
(1 to: 10) do: [ :element | n := n + element ].
n −→ 55
```
collect: applique un bloc à chaque élément et retourne une nouvelle collection avec les résultats.
```bash
Exemple : 
(1 to: 10) collect: [ :each | each * each ] −→ #(1 4 9 16 25 36 49 64 81 100)
```

select: retourne une sous-collection avec les éléments qui satisfont une condition donnée.
```bash
Exemple : 
'Bonjour Pharo' select: [ :char | char isVowel ] −→ 'oouao'
```

reject: similaire à select:, mais retourne les éléments qui ne satisfont pas la condition.
```bash
Exemple : 
'Bonjour Pharo' reject: [ :char | char isVowel ] −→ 'Bnjr Phr'
```

detect: retourne le premier élément satisfaisant la condition.
```bash
Exemple : 
'Bonjour Pharo' detect: [ :char | char isVowel ] −→ $o
```

detect:ifNone: retourne le premier élément satisfaisant la condition. Si aucun élément ne satisfait la condition, un bloc de code par défaut est exécuté.
```bash
Exemple : 
'Bonjour Pharo' detect: [:char | char isVowel] ifNone: ['Aucune voyelle trouvée'].
```


## Comment j'ai trouvé ces informations : 

J'ai trouvé ces informations dans le mooc (en regardant les vidéos) et sur le site programmation.developpez.com 

# 2 - Apprendre les conditionnels dans Pharo :

## Ecrire des conditionnels dans Pharo :

Les conditionnels sont obtenues par l’envoi des messages ifTrue:, ifFalse: ou ifTrue:ifFalse: au résultat d’une expression booléenne.

```bash
Exemple : 

condition ifTrue: [ block ] : Exécute block si condition est vraie.
condition ifFalse: [ block ] : Exécute block si condition est fausse.
condition ifTrue: [ trueBlock ] ifFalse: [ falseBlock ] : Exécute trueBlock si condition est vraie, sinon falseBlock.
```

## Ce qui diffère par rappoet à d'autres langages de programmation : 

En Pharo, les conditionnels sont gérés via des blocs de code envoyés comme messages aux objets booléens, contrairement aux langages impératifs traditionnels qui utilisent des structures conditionnelles explicites comme if, else.

## Avantages et inconvénients de cette approche : 

- Pour les avantages : les blocs peuvent être passés comme arguments ou stockés dans des variables montre la flexibilité des blocs en Pharo, 

- Pour les inconvénients : les blocs peuvent rendre le code plus complèxe et difficile à lire.

## Comment j'ai trouvé ces informations : 

J'ai trouvé ces informations dans le mooc. 

# 3 - Apprendre comment créer des classes et des méthodes : 

## Créer une classe et des méthodes dans Pharo 

- Ouvrir le Browser -> System Browser 
- Créer un package 
- Créer une classe 
```bash
Exemple : 
Object << #MCounter
	slots: {#count};
	sharedVariables: {};
	package: 'MyCounter'
```
- Ajouter une méthode
```bash 
Exemple : 
Counter>>count: anInteger
      count := anInteger  
```

## Ou j'ai trouvé ces informations : 

L'année dernière, j'ai suivi le cours de méta, où nous avons déjà abordé la création de classes, de méthodes, et l'utilisation de l'IDE de Pharo. Cela m'a permis de mieux comprendre ces concepts et de les appliquer plus facilement cette année.

## Le programme que j'ai crée : 

MyCounter 

## Les problèmes que j'ai rencontré : 

J'ai rencontré des problèmes lors du push vers GitHub en raison de difficultés liées à l'authentification SSH.

## Lien GitHub : 

https://github.com/aityahiaM/MyCounter 

# 4 - Le style de codage Pharo : 

Le style de codage dans Pharo insiste sur la simplicité et la lisibilité.

## Règles communes du style de codage en pharo : 

- Méthodes courtes : les méthodes doivent etre courtes concises.
- Lisibilité : le code doit lisible et bien structuré
- Noms descriptifs : il faut utiliser des noms clairs et descriptifs pour les méthodes et les variables pour rendre le code auto-documenté. 
- Responsabilité unique : chaque méthode ou classe doit avoir une responsabilité unique
- Commentaires pertinents : Les commentaires doivent expliquer pourquoi une certaine approche est utilisée et non pas ce que le code fait

-> Et pour détecter certaines violations de règles on peut utiliser le débogueur 

## Exemples de code violant certaines règles : 

1- Noms peu descriptifs :
```bash
MyClass >> m1 [
    | a b c |
    a := 1.
    b := 2.
    c := a + b.
    ^c
]
```

2- Commentaires inutiles et redondants :

```bash
MyClass >> calculateSum [
    "Calculer la somme de deux nombres"
    | a b sum |
    a := 5. "Valeur du premier nombre"
    b := 10. "Valeur du deuxième nombre"
    sum := a + b. "Additionner les deux nombres"
    ^sum
]
```


# 5 - Extras : 

## Les cascades :

Les cascades permettent d'envoyer plusieurs messages à un meme objet dans une seule expression

```bash
Exemple : 

au lieu d'écrire : Transcript cr.
                   Transcript show: 1.
                   Transcript show: 2
on écrit :  Transcript 
              cr;
              show: 1;
              show: 2 
```
## Les block closures : 

Les block closures sont des blocs de code qu'on peut passer comme argument à des méthodes 

```bash
Exemple : 

[:x | x + 1] value: 5.
```



