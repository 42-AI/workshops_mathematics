# Feuille d'exerices 2: Fonctions de référence

## Objectifs:
L'objectif principal de cette série d'exerices est de vous familiariser avec un ensemble de fonctions classiques.

## :pencil2: Exercice 1: Échauffement
Le but de l'exercice est d'améliorer l'acquisition des connaissances sur les fonctions.
### Partie 1: Images et antécédents
Rien de nouveau ici, juste des fonctions différentes.
0. Donner les ensembles de définition et image des fonctions suivantes:
$$
f(x) = x^2, \quad g(x) = \frac{1}{x} \\
\quad h(x) = x + 1, \quad i(x)=\sqrt{x}
$$
Pourquoi la fonction $g$ n'est pas définie en $x=0$ ?
1. Calculer les images par les fonctions précédentes, des nombres présents dans la liste (si c'est possible) $X = [-5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5]$
2. Tracer les représentations graphiques des fonctions $f$, $g$, $h$ et $i$.
3. Considérons la fonction $f_1$:
   $$
   f_1(x) = \sqrt{x}+2
   $$
   1. Déterminer les antécédents des valeurs suivantes: 2, 4, 14 et 14.5.
   2. Existe-t-il des antécédents pour les valeurs apppartenant à l'intervalle $]\infty ; 0]$ ? Pourquoi ?
4. Même chose pour la fonction $f_2$:
   $$
   f_2(x) = \sqrt{x+4} 
   $$
   1. Déterminer les antécédents des valeurs suivantes: 0, 2, 4, 14 et 25.
   2. Existe-t-il des antécédents pour les valeurs apppartenant à l'intervalle $[-4 ; 0]$ ?
   3. Sur quel intervalle la fonction $f_2$ n'est pas définie ?
5. De même que pour la fonction $f_3$:
   $$
   f_3 = \frac{1}{4}x^2
   $$
   1. Déterminer les antécédents des valeurs 2, 3, 4, 5 et 6.
   2. Donner le domaine image de la fonction $f_3$.

6. Et enfin pour la fonction $f_4$:
   $$
   f_4 = 2x^2 - 16
   $$
   1. Déterminer les antécédents des valeurs 2, -16, -8, 0 et 34.
   2. Donner le domaine image de la fonction $f_4$.

## :snake: Exercice 2: Tableau de valeurs et représentation graphique
Nous continuons l'étude des fonctions avec encore des tableaux de valeurs et les représentations graphiques.\
Nous allons également aborder la notion de parité pour les fonctions.\
L'objectif est de renforcer votre capacité d'analyse sur les fonctions, développer votre intuition en quelque sorte.

---
Concernant la parité.
Les fonctions qui sont possiblement paires impaires doivent au préalable avoir un **domaine de définition $D_f$** que l'on qualifie de **symétrique**.\
Un domaine de définition (*plus largement un ensemble*) est symmétrique si pour **tout nombre de ce domaine, son opposé appartient aussi au domaine**.\
Toute fonction dont le domaine de définition n'est pas symmétrique ne peut ni être paire ni impaire.\
Ainsi les fonctions racines où la racine est paire, comme par exemple:
$$
f(x) = \sqrt{x}, \quad g(x) = \sqrt[4]{x}, \quad h(x) = \sqrt[6]{x}
$$
ne peuvent pas être paire pu impaire car leurs domaines de définition sont $\mathbb{R}^+$.

Enfin,\
**une fonction $f$ est dite paire**, si son domaine de définition $D_f$ est symmétrique et si pour tout $x\in D_f$:
$$
f(-x) = f(x)
$$
**une fonction $f$ est dite impaire**, si son domaine de définition $D_f$ est symmétrique et si pour tout $x\in D_f$:
$$
f(-x) = - f(x)
$$

Pour finir sur la parité, il peut être noté une particularité graphique.
Les fonctions **paires** sont **symmétriques par rapport à l'axe des ordonnées**.\
Quant aux fonctions **impaires**, elles sont **symmétriques par rapport au point d'origine du repère** (point de coordonnées $(0; 0)$).

<p align="center">
<img src="assets/serie_2_exo_2_figure_1.png" width="400" alt="exemple exo 1" />
</p>
Les courbes en bleues sont des représentations graphiques de fonctions paires et les coutbes en rouges/oranges sont les représentations graphiques de fonctions impaires.\

*Vous vous demandez probablement à quoi cela peut vous servir pour faire du ML. Et bien cela peut vous aider à choisir un ou plusieurs modèles avant de les entraîner.
Un choix cohérent de modèle présage un meilleur score une fois le modèle entraîné.*

---
## Partie 1: [title]
[axer sur la reconnaissance graphique du caractère paire impaire ou ni l'un ni l'autre]

## Partie 2: [title]
[Coder une fonction de vérification de parité]

## Partie 3 [title]
[Étude d'une fonction paire ou impaire plus compliquée avec résolutions d'inégalitées à faire en codant.]

## :snake: Exercice 3 : [title]
[Proposer 3 problèmes pour montrer la mise en équation de situation: 1 problème géométrique, 1 problème économique (gain/dépense ou autre) ...]
[Donner une représentation graphique de données (points) demander de choisir un modèle et de fixer à la main les paramètres pour qu'il trouve le meilleur modèle. Jouer sur paire/impaire pour les données pour qu'ils aient un cas d'un modèle paire à choisir, puis impaire, puis compliqué.]

### Partie 1: 


### Partie 2: 


### Partie 3: 

