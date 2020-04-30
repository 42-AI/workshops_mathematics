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

*Vous vous demandez probablement à quoi cela peut vous servir pour faire du ML. Et bien cela peut vous aider à choisir un ou plusieurs modèles avant de les entraîner.\
Notamment, après une étape de standardisation des données, il est possible d'observer si les données peuvent être modélisé par une fonction paire, impaire ou n'ayant sans parité.\
Un choix cohérent de modèle participe à l'obtention d'un score plus faible une fois le modèle entraîné.*

---
## Partie 1:
Vous allez vous exercer à la reconnaissance de la parité des fonctions visuellement et à partir de l'expression algébrique.\
1. Pour chacune les fonctions représentées ci dessous, préciser lesquelles sont paires, impaires où ni l'une ou l'autre.

<p align="center">
<img src="assets/serie_2_exo_2_figure_2.png" width="300" alt="graph ex02 fig 2" />
<img src="assets/serie_2_exo_2_figure_3.png" width="300" alt="graph ex02 fig 3" />
<img src="assets/serie_2_exo_2_figure_4.png" width="300" alt="graph ex02 fig 4" />
</p>

2. À partir des expressions algébriques des fonctions suivantes, déterminer lesquelles sont paires, impaires ou ni l'un ni l'autre. Le domaine de définition des différentes fonctions est $\mathbb{R}$.
$$
f_1(x) = x^2 +4, \quad f_2(x) = -2x - 3 \quad f_3(x) =  x^2 + 1\\
f_4(x) = -2x^2 + x \quad f_5(x) =  \quad f_6(x) = \frac{1}{x^2} \\
f_7(x) = \frac{2}{x + 1} \quad f_8(x) = \sqrt{|x|} \quad f_9(x) = 3x^3\sqrt{|x|}\\
$$

## Partie 2: Coding time !
Coder une fonction python capable de dire si une fonction est possiblement paire ou impaire ou sans parité.\

Il vous faut prendre en compte 2 choses:
* le domaine de définition de la fonction,
* le *"comportement"* de la fonction pour $x$ et $-x$.

Dans la librairie sympy, il n'y a (à la connaissance de l'auteur des exercices) pas de fonction permettant de donner le domaine de définition de la fonction, uniquement le domaine de continuité (** continuous_domain **).\
Ainsi, vous ne devrez pas vérifier la condition de symmétrie du domaine de définition de la fonction.

1. Coder une fonction qui permet de dire (sans que ça soit démontrer, donc ça reste une supposition) si la fonction est paire, impaire ou sans parité.
``` python
def parity_guess(f, nb_list):
   """
   Arguments:
      f : a function or an expression.
      nb_list : a list of positive numbers.
   Description:
      The function calculate the image by the function of each numbers and its opposite values.
      Then the function compares the 2 lists of images to conclude on the guess of the parity.
   Return:
      "La fonction semble paire"
      La fonction semble impaire"
      "La fonction n'a pas de parité"
   """
```
2. **Version dure : (facultatif)** 
   Une version améliorer du code peut être faite en prenant en compte le domaine de définition.
   Une manière d'obtenir le domaine de définition est de résoudre les 3 équations suivantes:
   $$
   \begin{matrix}
     f(x) & > & 0 \\
     f(x) & = & 0 \\
     f(x) & < & 0 \\
   \end{matrix}
   $$
   et d'unir les intervalles de chaque équation.\
   Il faut ensuite vérifier que le domaine est symmétrique.
   Ensuite il faut vérifier si l'expression de la fonction est invariable en substituant $x$ par $-x$ ou bien déterminer que les expressions de $f(x) +f(-x)$ ainsi que $f(x) - f(-x)$.
   *(Un peu compliqué, donc je ne le recommande que pour ceux les plus motivés et/ou à l'aise)*\
   Voici un petit coup de pouce pour ceux qui tenterai de le faire, vous pouvez regarder les éléments suivants.
   
   ```python
   sympy.Symbol
   sympy.Lambda
   sympy.Intersection
   sympy.Union
   sympy.expr
   sympy.subs
   ```

## :snake: Exercice 3 : Trouver le bon modèle
Pour les 2 parties suivantes, l'objectif est de trouver les modèles les plus pertinents.

### Partie 1: 
Une entreprise produit et vend des boules de Nöel. Le prix unitaire est fixé entre $1$ et $10$ €. Le gérant a effectué une étude sur la recette (en milliers d'euros) issue de différentes boules en fonction du prix de vente de celles-ci (vous trouverez les données dans le fichier data_analysis_practise_sheet_2_ex03.csv)

<p align="center">
<img src="assets/serie_2_exo_3_figure_5.png" width="400" alt="graph ex03 fig 4" />
</p>

1. Tracer l'évolution de la recette quotidienne en fonction du prix de vente unitaire pour chaque boule de Noël.
2. Tracer l'évolution de la recette quotidienne moyenne en fonction du prix de vente unitaire pour toutes les boules de Noël.
3. Proposer un modèle pouvant décrire l'évolution de la recette moyenne.
4. Représenter le modèle avec les données et plusieurs autres modèles que vous jugez moins bon pour prédire la l'évolution de la recette quotidienne.


### Partie 2: 



