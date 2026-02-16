# Transformée en z inverse

## Principe

On considère $H(z)$ une transformée en $z$ qui se présente sous la forme d'une fraction rationnelle en $z^{-1}$ et on recherche la séquence temporelle $h(n)$ associée. Sur un exemple traité, on accèdera à la solution via une décomposition en éléments simples, sous la forme

$$h(n)=\sum_{k=0}^{K-1} A_k \times P_k^n$$

lorsque les $K$ pôles $P_k$ sont tous d'ordre de multiplicité égal à 1.

Sous cette hypothèse, la décomposition en éléments simples se présente en effet sous la forme

$$H(z)=\sum_{k=0}^{K-1} \dfrac{A_k}{1-P_kz^{-1}}$$

Par ailleurs, le tracé de $h(n)$ peut simplement être obtenu en appliquant une entrée $\delta(n)$ (impulsion numérique qui vaut $1$ pour $n=0$ et $0$ sinon) à la fonction de transfert $H(z)$.

Par extension, les pôles d'ordre 2 peuvent aussi être traités. Un pôle $P_k$ d'ordre 2 est associé au terme ci-dessous dans $h(n)$.

$$A_{k,2} \times (n+1) \times P_k^n + A_{k,1} \times P_k^n$$

Il correspond au terme ci-dessous dans la décomposition en élément simple de $H(z)$.

$$\dfrac{A_{k,2}}{(1-P_kz^{-1})^2} + \dfrac{A_{k,1}}{1-P_kz^{-1}}$$

## Méthode utilisée

Voir la page Wikipédia [Décomposition en éléments simples](https://fr.wikipedia.org/wiki/D%C3%A9composition_en_%C3%A9l%C3%A9ments_simples#%C3%89l%C3%A9ments_simples_associ%C3%A9s_%C3%A0_un_p%C3%B4le_multiple) à la rubrique **Éléments simples associés à un pôle multiple**.

Le changement de variable envisagé dans cette méthode est plutôt de la forme $y = 1-P_k x$ avec $x = z^{-1}$ afin de conserver le principe d'utiliser les expressions en $x = z^{-1}$.

$$H(z)=\sum_{k=0}^{K-1} \sum_{m=1}^{M_k} \dfrac{A_{k,m}}{(1-P_kz^{-1})^m}$$

## Le Notebook

Le [Notebook](tzinv.ipynb) pour les pôles d'ordre 1 à 4 est disponible sur ce dépôt.

Par ailleurs, on peut disposer aussi de [la version sur Google Colab](https://colab.research.google.com/drive/1lougOsX4DbZTJ-A5Ba6NEc-LAG60jZih?usp=sharing).

## Conjecture utilisée

La séquence $h(n)$ associé au terme

$$\dfrac{A_{k,M}}{(1-P_k z^{-1})^M}$$

pour $M \geq 2$ est

$$h(n)=A_{k,M}\left[\dfrac{\prod_{m=1}^{M-1}(n+m)}{(M-1)!}\right] P_k^n$$

## Annexe

La raison pour laquelle on envisage d'utiliser plutôt des expressions en $z^{-1}$ est liée au fait qu'elles permettent notamment d'accéder facilement à l'équation aux différence dans le domaine temporel.

Pour une fonction de transfert $H(z)$ de la forme

$$H(z)=\dfrac{\sum_{m=0}^{M}b_mz^{-m}}{1+\sum_{k=1}^{K}a_kz^{-k}}=\dfrac{Y(z)}{X(z)}$$

l'équation aux différence associée est (avec $x(n-m)=0$ pour $n-m<0$ et $y(n-k)=0$ pour $n-k<0$)

$$y(n) = \sum_{m=0}^{M}b_mx(n-m) - \sum_{k=1}^{K}a_ky(n-k)$$

C'est l'équation mise en œuvre par la fonction [**lfilter**](https://docs.scipy.org/doc/scipy/reference/generated/scipy.signal.lfilter.html) de scipy (en particulier avec $x(n)=\delta(n)$ dans les notebooks).
