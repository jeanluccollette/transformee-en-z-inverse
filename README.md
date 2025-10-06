# Transformée en z inverse

## Principe

On considère $H(z)$ une transformée en $z$ qui se présente sous la forme d'une fraction rationnelle en $z^{-1}$ et on recherche la séquence temporelle $h(n)$ associée. Sur un exemple traité, on accèdera à la solution via une décomposition en éléments simples, sous la forme

$$h(n)=\sum_{k=0}^{K-1} A_k \times P_k^n$$

lorsque les $K$ pôles $P_k$ sont tous d'ordre de multiplicité égal à 1.

Sous cette hypothèse, la décomposition en éléments simples se présente en effet sous la forme

$$H(z)=\sum_{k=0}^{K-1} \dfrac{A_k}{1-P_kz^{-1}}$$

Par ailleurs, le tracé de $h(n)$ peut simplement être obtenu en appliquant une entrée $\delta(n)$ (impulsion numérique qui vaut $1$ pour $n=0$ et $0$ sinon) à la fonction de transfert $H(z)$.

Par extension, les pôles d'ordre 2 peuvent aussi être traités. Un pôle $P_z$ d'ordre 2 est associé au terme ci-dessous dans $h(n)$.

$$(n+1) \times A_{k2} \times P_k^n + A_{k1} \times P_k^n$$

$$\dfrac{A_k2}{(1-P_kz^{-1})^2} + \dfrac{A_k1}{1-P_kz^{-1}}$$

## Les Notebooks

Le [Notebook](tzinv_ordre1.ipynb) pour les pôles d'ordre 1 est disponible sur ce dépôt.

Par ailleurs, on peut disposer aussi de [la version sur Google Colab](https://colab.research.google.com/drive/1apsHT_S6EJ6aIAlqmrPvxvE24gnwubkB?usp=drive_link).

Le [Notebook](tzinv_ordre2.ipynb) pour les pôles d'ordre 1 ou 2 est disponible sur ce dépôt.

Par ailleurs, on peut disposer aussi de [la version sur Google Colab](https://colab.research.google.com/drive/1-FxWG_sAFUHAgCftML5VYthL1JakQ7O5?usp=drive_link).
