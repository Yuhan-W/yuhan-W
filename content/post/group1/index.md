---
title: Groups (Ⅰ)
subtitle: Abstract algebra

# Summary for listings and search engines
summary: This article is about quotient groups and homomorphisms of groups.

# Link this post with a project
projects: []

# Date published
date: "2020-12-13T00:00:00Z"

# Date updated
lastmod: "2020-12-13T00:00:00Z"

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: ''
  focal_point: ""
  placement: 1
  preview_only: false

authors:
- admin

tags:
- Group theory

categories:
- Math
- Abstract Algebra
---

## Subgroups and quotient groups

In this section, we shall study normal subgroups and quotient groups, which play an important role in understanding the properties of groups. 

### Definition 1
If $H$​​​​​ is a nonempty subset of group $G$​​​​ and $H$ is itself a group under the operation in $G$, then $H$ is said to be a **subgroup** of $G$, denoted $H<G$​​.

### Definition 2
Let $H$ be a subgroup of group $G$, and $a, b\in G$. If $ab^{-1} \in H$, $a$ is **right congurent** to $b$ **modulo** $H$, denoted $$a\equiv_r b(\bmod H)$$ Similarly, a is **left congurent** to $b$ **modulo** $H$ if $a^{-1}b \in H$, denoted $$a\equiv_l b(\bmod H)$$

Now we have two kinds of equivalence relations on group $G$: right/left congurence modulo $H$ (easy to prove). So it is a natural idea that we can create a quotient set $G/H$ based on the obtained equivalence relation.

### Theorem 1
The equivalence class of $a\in G$ under right(left) congurence modulo $H$ is $$Ha=\lbrace ha\ |\ h\in H\rbrace \Big(aH=\lbrace ah\ |\ h\in H\rbrace\Big)$$
**Proof** The equivalence class of $a\in G$ under right congurence modulo $H$ is $$\begin{align*}\{b\in G \ |\ b\equiv_r a(\bmod H)\}&=\{b\in G\ |\ ba^{-1}\in H\}\\\\&=\{b\in G\ |\ ba^{-1}=h\in H\}\\\\&=\{b\in G\ |\ b=ha;h\in H\}\\\\&=\{ha\ |\ h\in H\}=Ha \ \ \ \square\end{align*}$$ 
Now a quotient set $G/H$ containing right cosets (or left cosets) is created, but we do not know whether $G/H$ is a group under the binary operation in $G$. An ideal case is that for $\forall Ha, Hb\in G/H$, we have $Ha\cdot Hb=Hab$, which makes $G/H$ is a group under the binary operation in $G$. A certain kind of subgroups make this possible.

### Theorem 2
Let $H$ be a subgroup of $G$. The following conditions are equivalent.

1. Left and right congurence modulo $H$ conicide.
2. $aH=Ha, \forall a\in G$
3. $\forall a\in G, h \in H, aha^{-1}\in H$
4.  $\forall a, b \in G$, we have $Ha\cdot Hb=Hab$

**Proof**
(1) $\Leftrightarrow$ (2) is trivial, (2) $\Rightarrow$ (3)$$ah_1=h_2 a\Rightarrow h_2=ah_1a^{-1}\in H$$ 
(3) $\Rightarrow$ (4) $$Ha\cdot Hb=H(Ha)b=HH(ab)=Hab$$
(4) $\Rightarrow$ (2) is obvious.$\ \ \ \square$

### Definition 3
A subgroup $H$ is said to be a **normal subgroup** of group $G$ if it satisfies the equivalent conditions above.

Therefore, we are able to obtain a quotient set $G/H$ of group $G$ that is also a group under the binary operation in $G$ if $H$ is a normal subgroup of $G$.
## Homomorphisms 

### Definition 4
Let $G$​ and $G'$​ be groups. A function $f: G \rightarrow G'$​​​​​​​​​​ is a **homomorphism** provided $$ f(ab)=f(a)f(b),\ \  \  \forall a, b \in G $$​
$f$ is called an **isomorphism** if it is bijective.

It is apparent that $f:G\rightarrow G'$ is a monomorphism if and only if $\mathrm{Ker} f=\{e\}$, while the following theorem makes an isomorphism possible when $\mathrm{Ker} f\neq\{e\}$ by creating a quotient group $G/ \mathrm{Ker}\ f$ of group $G$.
### First Isomorphism Theorem
if $f:G \rightarrow G'$ is a homomorphism of groups, then $f$ induces an **isomorphism** $$G/ \mathrm{Ker}\ f\cong \mathrm{Im}\ f$$
**proof** Let $N=\mathrm{Ker}\ f$, $n \in N$. If $b\in aN$, then $f(b)=f(an)=f(a)f(n)=f(a)$. Therefore, we can define map $\bar f:G/N \rightarrow G'$ as $$\bar f(aN)=f(a)$$ Since $$\bar f(aNbN)=\bar f(abN)=f(ab)=f(a)f(b)=\bar f(aN)\bar f(bN)$$ $\bar f$ is a homomorphism and $\mathrm{Im}\ \bar  f=\mathrm{Im}\ f$. If $\bar f(aN)=\bar f(bN)$, then $$f(a)=f(b) \Rightarrow b\in aN \Rightarrow aN=bN$$. So $\bar f$ is a monomorphism. Let $G'=\mathrm{Im}\ f$. Now $\bar f$ is an epimorphism. Finally, an **isomorphism** $$\bar f:G/ \mathrm{Ker}\ f\rightarrow \mathrm{Im}\ f$$is induced.$\ \ \ \square$

## License

Released under the [MIT](https://github.com/wowchemy/wowchemy-hugo-modules/blob/master/LICENSE.md) license.