# Décomposition en éléments simples

## Introduction

La résolution d'équations différentielles linéaires peut s'effectuer en s'aidant de la transformée de Laplace. Via cette méthode, on accède dans un premier temps à la transformée de Laplace de la solution, qui se présente pour l'essentiel sous la forme d'une fraction rationnelle d'une variable complexe $p$.

Pour revenir à l'expression temporelle de la solution, il faut procéder à la **décomposition en éléments simples** de la fraction rationnelle en $p$, de sorte qu'apparaissent des termes élémentaires de la forme $\dfrac{K}{(p-a)^n}$ (dans le corps des complexes) pour lesquels l'expression temporelle associée $K\dfrac{t^{n-1}e^{at}\theta(t)}{(n-1)!}$ est connue.

L'idée ici est d'illustrer les méthodes de calcul via le package **sympy** de calcul symbolique. Mais il reste préférable de pouvoir **mener ces calculs avec un crayon et un papier**.

## Méthodes de calcul

### Cas d'un pôle $p_0$ simple

$$F(p)=\dfrac{P(p)}{Q(p)}=\dfrac{P(p)}{B(p)(p-p_0)}=K(p)+\dfrac{a_1}{(p-p_0)}$$

$$a_1=\dfrac{P(p_0)}{B(p_0)}=F(p)(p-p_0)|_{p=p_0}$$

### Cas d'un pôle $p_0$ d'ordre de multiplicité N supérieur à 1

$$F(s)=\dfrac{P(p)}{Q(p)}=\dfrac{P(p)}{B(p)(p-p_0)^N}=K(s)+\Sigma_{n=1}^N\dfrac{a_n}{(p-p_0)^n}$$

$$a_N=\dfrac{P(p_0)}{B(p_0)}=F(p)(p-p_0)^N|_{p=p_0}$$

$$F_{N-1}(p)=F(p)-\dfrac{a_N}{(p-p_0)^N}=K(p)+\Sigma_{n=1}^{N-1}\dfrac{a_n}{(p-p_0)^n}$$

$$a_{N-1}=F_{N-1}(p)(p-p_0)^{N-1}|_{p=p_0}$$

Par récurrence :

$$F_N(p)=F(p)$$

$$a_N=F(p)(p-p_0)^N|_{p=p_0}$$

Pour $n$ variant de $N$ à $2$ :

$$F_{n-1}(p)=F_n(p)-\dfrac{a_n}{(p-p_0)^n}$$

$$a_{n-1}=F_{n-1}(p)(p-p_0)^{n-1}|_{p=p_0}$$

## Le notebook

La version disponible sur ce dépôt :

[decomposition_en_elements_simples.ipynb](decomposition_en_elements_simples.ipynb)

Une version est par ailleurs disponible sur Google Colaboratory :

https://colab.research.google.com/drive/1A4cY4Jn0bs6mrR9nHLJFfoRX71Qcf5_s?usp=sharing
