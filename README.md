# Transformée en z inverse

## Principe

On considère $H(z)$ une transformée en $z$ qui se présente sous la forme d'une fraction rationnelle en $z^{-1}$ et on recherche la séquence temporelle $h(n)$ associée. Sur un exemple traité, on accèdera à la solution via une décomposition en éléments simples, sous la forme

$$h(n)=\sum_{k=0}^{K-1} A_k \times Z_k^n$$

lorsque les $K$ pôles $Z_k$ sont tous d'ordre de multiplicité égal à 1.

Sous cette hypothèse, la décomposition en éléments simples se présente en effet sous la forme

$$H(z)=\sum_{k=0}^{K-1} \dfrac{A_k}{1-Z_kz^{-1}}$$

Par ailleurs, le tracé de $h(n)$ peut simplement être obtenu en appliquant une entrée $\delta(n)$ (impulsion numérique qui vaut $1$ pour $n=0$ et $0$ sinon) à la fonction de transfert $H(z)$.

## Le Notebook

Le [Notebook](tzinv.ipynb) est disponible sur ce dépôt.

Par ailleurs, on peut disposer aussi de [la version sur Google Colab](https://colab.research.google.com/drive/1SX8pW15GO1v-1lPUa5QzlkLz-NX1Wcjw?usp=drive_link).
