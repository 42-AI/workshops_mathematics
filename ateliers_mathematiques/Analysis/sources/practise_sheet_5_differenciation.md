# Feuille d'exerices 5: dérivation de fonction à une seule variable

## Objectifs:
L'objectif principal de cette série d'exerices est de vous entraîner à dériver des fonctions à une seule variable.
Lorsque vous réaliserez vos modèles, ceux-ci peuvent être basés sur des fonctions très diverses, de même que la fonction de coût qui peut être la distance quadratique moyenne ou bien une toute autre fonction.


### Préambule:
Dans votre cursus classique, vous étudiez la notion de de taux de variation, puis la dérivée d'une fonction en un point, suivi de la détermination de la tangente d'une fonction en un point d'abscisse $a$ et cela en long et en large.\
Ces notions sont importantes à comprendre pour saisir le sens de la dérivation, mais la notion sur laquelle nous allons nous attarder le plus est la détermination de l'expression dérivée d'une fonction.\
La dérivation d'une fonction vous sera utile pour déterminer l'expression de la dérivée de la fonction de coût, mais également pour déterminer le vecteur Jacobien et la matrice Hessienne que nous verrons plus tard à la fin de la partie sur l'algèbre.

## :pencil2: :snake: Exercice 1
Cette exercice traite de la notion du taux de variation.\
L'objectif est que vous compreniez quelle information donne le taux de variation et quelles informations le taux de variation ne donne pas.

### Partie 1:
Sur la figure ci-dessous est représenté la fonction $f$ d'équation:
$$
f(x) = x^3-6x^2+4x+12
$$
Calculer le  taux de variations entre les points
* $(-5, f(-5))$ et $(-3, f(-3))$,
* $(-3, f(-3))$ et $(-2, f(-2))$,
* $(-3, f(-3))$ et $(0, f(0))$,
* $(0, f(0))$ et $(1, f(1))$,
* $(0, f(0))$ et $(4, f(4))$,
* $(4, f(4))$ et $(7, f(7))$,\
*Évidemment vous devez calculer in fine les valeurs de la fonction pour les différents points mentionnés*\
Petite précision, lorsque l'on vous dit de calculer le ** taux de variation entre le points $\mathbf{(a, f(a))}$ et $\mathbf{(b, f(b))}$ **
cela donne:
$$
\tau_f(a,b) = \frac{f(b)-f(a)}{b-a}
$$

<p align="center">
<img src="assets/serie_5_exo_1_figure_1.png" width="400" alt="Exercice 1" />
</p>

Que pouvez-vous dire entre le taux de variation et l'évolution de la fonction ? Y-a-t-il un lien entre le taux de variation de la fonction entre 2 points et l'évolution de la fonction entre ceux-ci ? 

### Partie 2:
Calculer maintenant le taux de variation entre les points $(-2, f(-2))$ et $(6,f(6))$. Le taux de variation calculé donne-t-il l'information que la fonction est croissante, décroissante puis recroissante sur l'intervalle $[-2;6]$ ? L'information sur l'évolution obtenue par le taux de variation est de quelle nature ? (locale ?, globale ?, instantannée ?, moyennée ?)

### Partie 3:
Vous devez coder une fonction permettant de calculer le taux de variation d'une fonction.
1. Dans un premier temps, la fonction recevra en paramètre 2 tuples de 2 nombres:
   ```python
    def variation_rate(tuple_A, tuple_B):
        """
        Parameters
            tuple_A : tuple of 2 numbers corresponding to x and y of point A.
            tuple_B : tuple of 2 numbers corresponding to x and y of point B.
        Description:
            Function calculates the variation rate between A and B.
        Return:
            tau_AB: variation rate between A and B.
        """
    
    import sympy as sy
    x = sy.Symbol('x')
    f = 3*x + 12
    A = (1, f.subs(x,1))
    B = (2, f.subs(x,2))
    
    variation_rate(A,B)
    # Output:
    3.0
   ```

2. Coder une version améliorée de la fonction ```variation_rate``` qui prendra 3 paramètres:
   * une liste ou une tuple de 2 nombres délimitant l'intervalle où l'on calcul le taux de variation,
   * une fonction,
   * un nombre exprimant le nombre de segment subdivisant l'intervalle pour lesquels le taux de variation est calculé.
  ```python
    def variation_rate(interval, f, nb_seg):
        """
        Parameters
            tuple_A : tuple of 2 numbers corresponding to inf and max of the interval.
            f : expression of a function.
            nb_seg: number of segments on which variation rate will be calculated
        Description:
            Function calculates the nb_seg variation rate of f on interval.
        Return:
            list containing the abcissas, values fonctions and variation rate:
            [x1, x2, f(x1), f(x2), (f(x2) - f(x1))/(x2 - x1)]
        """
    
    import sympy as sy
    x = sy.Symbol('x')
    f = 3*x + 12
    interval =  (0, 5)
    
    variation_rate(interval,f, 5)
    # Output:
    [[0, 1, 12, 15, 3], [1, 2, 15, 18, 3], [2, 3, 18, 21, 3], [3, 4, 21, 24, 3], [4, 5, 24, 27, 3]]

   ```

## :pencil2: :snake: Exercice 2

### Partie 1
Nous allons étudier le lien entre taux de variation et nombre dérivée en un point à l'aide de la formule de la limite:
$$
f'(a) = \lim_{\delta \rightarrow 0} \frac{f(a+\delta) + f(a)}{\delta}
$$

Pour cela, considère la fonction:
$$
f(x) = 3x^3 - 6x^2 + 5
$$
et calculer le taux de variation de f en différents abscisses et pour des couples de points de plus en plus proche.
1. Calculer le taux de variation de la fonction pour les points d'abscisses $-1$, $0$ et $1$ pour $\delta$ étant égale à $1$, $0.1$, $0.01$ et $0.001$.
2. Montrer que la dérivée de la fonction f a pour expression:
$$
f'(x) = 9x^2 - 12x
$$
1. Calculer les valeurs de $f'(x)$ pour x égal à $-1$, $0$ et $1$.
2. Vers quelles valeurs tendent les taux de variation de f en $-1$, $0$ et $1$ ?

### Partie 2:
La notion de tangente est liée à celle de dérivée.
En effet, l'équation d'une tangente à une fonction au point d'abscisse $a$ est donnée Rattacher la dérivée en un point avec la tangente d'une fonction en un point.
$$
f'(a)(x-a) + f(a)
$$

1. Donner les expressions des tangentes à la fonction $f$ aux points d'abscisses $-2$, $0$ et $2$
Pour rappel, l'expression de la tangente d'une fonction $f$ au point d'abscisse $a$ est:
$$
t_f(x) = f'(a)(x-a) + f(a)
$$
1. À l'aide de la librairie **matplotlib.pyplot** tracer la fonction $f$ ainsi que les tangentes aux différents points d'abscisses $-2$, $0$ et $2$.

2. Coder une fonction permettant de déterminer l'expression de la tangente (utiliser la méthode diff au sein de **sympy**):
   ```python
    def tangent(f, a):
        """
        Parameters
            f : expression of a function.
            a: abscissa where the tangent is calculated.
        Description:
            Function calculates the tangent.
        Return:
            the expression of the tangent at a.
        """
    
    import sympy as sy
    x = sy.Symbol('x')
    f = 3*x**2 + 12
    tangent(f, 5)
    # Output:
    30x-63
   ```
   À l'aide de la fonction ```tangent```  calculer la tangente des fonctions suivantes:
   $$
   f(x) = \frac{1}{2}x^2 + 3 \\
   g(x) = \frac{1}{3}x^3 + \frac{1}{2}x^2 + x \\
   h(x) = \frac{1}{4}x^4 - 3x^3 + 2x  -6 
   $$ 
   aux points de d'abscisses $-1$, $0$, $1$ et $4$.\
   Tracer sur 3 figures différentes les fonctions et leurs tangentes aux différents points.\
Observez que les pentes des tangentes aux courbes des fonctions, aux points concernés, correspondent aux taux de variations ("instantanées") des fonctions en ces points.

## :pencil: Exercice 3:
Dans cette exercice, vous allez vous entraînez à dériver quelques fonctions.
Le but n'étant pas de faire de vous des experts de la dérivation, sympy le fait très bien, et en une seule commande : ```sympy.diff```. L'objectif est donc que vous saisissiez le concept de dérivation et que vous puissiez manipuler la dérivation au cours de vos raisonnements futur sur la bonne vieille feuille de papier.

Afin de vous faciliter la vie avec la dérivation, connaître un minimum de dérivée usuelle et quelques règles de dérivation n'est pas du luxe, et c'est ce que nous allons voir.

### Partie 1: Dérivée d'une somme de fonction
La première règle de dérivation est que la dérivée d'une somme de fonction est égale à la somme des dérivées des fonctions.\
$$
\frac{d}{dx}(f(x)+g(x)) = \frac{df}{dx} + \frac{dg}{dx}
$$
Calculer les dérivées des fonctions suivantes:
$$
f_1(x) = \frac{1}{2}x^2 \quad \quad f_2(x) = 3x^3 \quad \quad f_3(x) = 2\sqrt{x}\\
f_4(x) = 3x^3 + 2x \quad \quad f_5(x) = 3x^3+ 5x^2 + 6x + 1 \quad \quad f_6(x) = 2\sqrt{x}+ \frac{1}{16}x^4 + \frac{1}{x}\\
f_7(x) = x^10 + \frac{1}{x^5} - 5\sqrt{x} \quad \quad f_8(x) = \sum_{i=1}^{N}ix^i \quad \quad f_9(x) = \sum_{i=1}^{N}\frac{i}{x^i} \\
$$

### Partie 2: Dérivée d'un produit de fonctions
La seconde règle de dérivation concerne la dérivée d'un produit de fonctions. Celle-ci est définie telle que:
$$
\frac{d}{dx}(f(x)\times g(x)) = \frac{df}{dx}\times g(x) + f(x) \times \frac{dg}{dx}
$$
Calculer les dérivées des fonctions suivantes:\

---
**Note:**
$$ \frac{d}{dx} \left( cos(x)\right) = -sin(x) \quad \quad \frac{d}{dx} \left( sin(x)\right) = cos(x)$$

---

$$
f_1(x) = \left(\frac{1}{2}x^2 \times \sqrt{x}\right) \quad \quad f_2(x) = 3x^3\times cos(x) \quad \quad f_3(x) = 2\sqrt{x}\times sin(x)\\
f_4(x) = cos(x)\times sin(x) \quad \quad f_5(x) = x^4\times cos(x)\times \sqrt{x} \quad \quad f_6(x) = ln(x)\times e^x\\
$$

### Partie 3: Dérivée d'une composition de fonctions
La troisième règle de dérivation concerne la composition de fonctions. Celle-ci est définie telle que:
$$
\frac{d}{dx}(f(u(x)) = u'(x)\times f'(u(x)) 
$$
Calculer les dérivées des fonctions suivantes:

$$
f_1(x) =  3\left(x^2 + 1\right)^2 \quad \quad f_2(x) = 3\left(x^5 + 1\right)^3 \quad \quad f_3(x) = \sqrt{\frac{1}{2}x^2}\\
f_4(x) = (2\sqrt{x}- 3)^4 \quad \quad f_5(x) = \frac{2}{x^2-5} \quad \quad f_6(x) = e^{3x^3 -1}\\
$$