# Feuille d'exerices 3: Somme et produit généralisées

## Objectifs:
L'objectif principal de cette série d'exerices est de vous entraîner à manipuler les sommes et produits généralisées ainsi que la notation d'Einstein largement utilisé en mathématiques et que l'on retrouve dans le formalisme du machine learning.


## :pencil2: Exercice 1:
Dans cette exercice vous allez devoir expliciter les sommes et produits généralisées ci dessous.
$$
    (1)\ \sum_{i = 1}^{4}2i  \quad \quad \quad (2)\ \prod_{j=1}^{5} \left(\frac{1}{2}\right)^j \\
    (3)\ \sum_{k = 1}^{5} (5-k)^k \quad \quad \quad (4) \ \prod_{l=0}^{5}\left(\frac{1}{2+l}\right)^{2l} \\
    (5)\ L(X,Y,\mathbf{\theta}) = \frac{1}{5}\sum_{i = 0}^{4}\left(f(x_i,\mathbf{\theta})-y_i\right)^2  \quad \quad \quad  (6)\ \prod_{n=0}^{3}(n-x)^2  \\
    (7)\ f(x) = \sum_{n = 1}^{5} \frac{f^{(n)}(x_0)}{n!}(x-x_0)^n \quad \quad \quad  (8)\ L(X,Y,\mathbf{\theta}) = -\sum_{l=0}^{5} y_i\log(f(x_i,\mathbf{\theta}))
$$

Les formules $(5)$, $(7)$ et $(8)$ sont des formules que vous pourriez rencontrer un jour en faisant du ML.
En effet, la formule 5 correspond à la formule de l'erreur quadratique moyenne (MSE), la formule $(7)$ correspond au développement en série de Taylor, utilisé lorsque l'on utilise un polynôme afin d'approximer une fonction au voisinage d'un point. Enfin, $(8)$ est une formule de fonction de coût pour un problème de classification (*categorical cross-entropy*).

## :pencil2: Exercice 2:
1. Pour les expressions ci-dessous, développer explicitement les sommes:
$$
\sum_{i = 1}^{3}\sum_{j = 1}^{2} (i+j) \quad \quad \sum_{k = 1}^{3}\sum_{l = 0}^{2} (-1)^{k}\frac{k+l}{2^l} 
$$

2. Écrire sous la forme de somme généralisée les expressions suivantes:
$$
(1)\ \mathcal{S}_1 = 1 + 2 + 3 + 4 + 5 + 6\\
(2)\ \mathcal{S}_2 = 2 + 4 + 6 + 8 + 10 + 12 + ... + 40 + 42 \\
(3)\ \mathcal{S}_3 = a_1 + a_2 + a_3 + a_4 + a_5 \\
(4)\ \mathcal{S}_3 = 1 + 2 + 4 + 8 + 16 + 32 + 64 + 128  \\
(5)\ \mathcal{S}_5 = a_1.b_1 + a_2.b_2 + a_3.b_3 + a_4.b_4 + a_5.b_5 \\
(6)\ \mathcal{S}_6 = a_1.b_1 + a_2.b_2 + ... + a_{n-1}.b_{n-1} + a_n.b_n +2n\\
(7)\ \mathcal{S}_7 = 1 - \frac{2}{3} + \frac{4}{5} - \frac{8}{9} + \frac{16}{17} - \frac{32}{33} \\
$$

## :pencil2: Exercice 3: 
Dans cet exercice, vous allez manipuler la convention de notation d'Einstein.
1. Les expressions suivantes utilisent la notation d'Einstein. Explicité ces expressions dans un premier temps puis reformulez les en utilisant la somme généralisée.
$$
(1)\ b_{ii} \quad (i \in \{1, 2, 3, 4, 5\}),\\
(2)\ a_{1j}b_{j1} \quad (j \in \{1, 2, 3, 4\}),\\
$$

---
Si vous continuez dans le domaine de l'IA ou que vous continuez à vous formez en mathématiques, il arrivera un jour ou vous tomberez dans un premier temps sur le symbole de Kronecker, puis celui de Levi-Civita (dans cet ordre exactement !).
### Symbole de Kronecker:
Le symbole de Kronecker est une fonction à 2 variables notée $\delta$, avec les 2 variables disposées en indices (le plus souvent): $\mathbf{\delta_{ij}}$.\
La particularité de cette fonction est qu'elle vaut $1$ si les 2 variables sont égales, $0$ sinon:
$$
\delta_{ij} = \bigg\{ \begin{matrix} 1,  \text{ si } i = j\\ 0,  \text{ si } i \ne j\end{matrix}
$$
---

$$
(3)\ b_{ij}\delta_{ij} + a_{ij}\delta_{i,j} \quad (i,j \in \{1, 2, 3, 4\}),\\
(4)\ a_{ij}b_{jk}\delta_{ik} \quad (i,j,k \in \{1, 2, 3\}),\\
$$

---
### Symbole de Levi-Civita:
Le symbole de Levi-Civita $\epsilon$ est un déterminant de matrice $(2,2)$ ou $(3,3)$ (dans la majorité des cas), usuellement noté $\varepsilon_{ij}$ ou $\varepsilon_{ijk}$ en fonction de la taille:
$$
\varepsilon_{ij} = 
\begin{vmatrix}
\delta_{i1} & \delta_{i2} \\
\delta_{j1} & \delta_{j2}
\end{vmatrix}\\
\varepsilon_{ijk} = 
\begin{vmatrix}
\delta_{i1} & \delta_{i2} & \delta_{i3} \\
\delta_{j1} & \delta_{j2} & \delta_{j3} \\
\delta_{k1} & \delta_{k2} & \delta_{k3}
\end{vmatrix}
$$
Ce qui donne:
$$
\varepsilon_{ij} = \Bigg\{
\begin{matrix}
1, & \text{ si } & (i,j) = (1,2)\\
-1,& \text{ si } & (i,j) = (2,1)\\
0, & \text{ si } & i=j
\end{matrix}\\
\varepsilon_{ijk} = \Bigg\{ 
\begin{matrix}
1, & si & (i,j,k) \text{ est } & (1,2,3), (2,3,1) \text{ ou } (3,1,2)\\
-1, & si & (i,j,k) \text{ est } & (1,3,2), (3,2,1) \text{ ou } (2,1,3)\\
0, & si & i=j \text{, ou } & j = k \text{, ou } i = k
\end{matrix}
$$
(*Vous voyez c'était bien le symbole de Kronecker d'abord puis celui de Levi-Civita ensuite !*)

---

$$
(5)\ b_{ij}\varepsilon_{ij} \quad (i,j \in \{1, 2, 3, 4\}), \\
(6)\ b_{ij}\delta_{ij} + b_{kl}\varepsilon_{kl} \quad (i,j,k,l \in \{1, 2, 3\})
$$