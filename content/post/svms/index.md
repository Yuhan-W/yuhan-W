---
title: 'Support Vector Machines: Preliminaries'
subtitle: Machine Learning

# Summary for listings and search engines
summary: Lagrange duality and kernel methods are discussed as preliminaries for understanding the basics of SVMs. 

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
- Statistical Learning

categories:
- Machine Learning
- Optimization
---


### Lagrange duality
Consider an optimization problem of the following form:
$$ \min_{w} f(w)$$
$$\begin{align*}
s.t.\ g_i(w)&\leq0,\ i=1, 2, \dots,k\\\\
h_i(w)&=0, \ i=1, 2,\dots, l\end{align*}$$
To solve this problem, we define the generalized Lagrangian:
$$ \mathcal{L}(w, \alpha, \beta) = f(w) + \sum_{i=1}^{k}\alpha_ig_i(w) + \sum_{i=1}^l \beta_ih_i(w).$$
Let's define a function $\theta_{\mathcal{P}}(w)$ as
$$\theta_{\mathcal{P}}(w)=\max_{\alpha, \beta:\alpha_i\geq0} \mathcal{L(w,\alpha,\beta)}.$$
If $w$ does not satisfies the constraints of the optimization problem above, it is clearly that
$$\theta_{\mathcal{P}}(w)=\max_{\alpha,\beta:\alpha_i\geq0} \Big(f(w)+ \sum_{i=1}^{k}\alpha_ig_i(w) + \sum_{i=1}^l \beta_ih_i(w)\Big)=\infty.$$
But if $w$ satisfies the constraints, then $\theta_{\mathcal{P}}(w)=f(w).$ As a result, it is not difficult to find that the following problem(called the primal problem) is equivalent to the original optimization problem:
$$\min_{w}\theta_{\mathcal{P}}(w)=\min_{w}\max_{\alpha, \beta:\alpha_i\geq0} \mathcal{L(w,\alpha,\beta)}.$$
Now we define another function $$\theta_{\mathcal{D}}(\alpha, \beta)=\min_w\mathcal{L}(w,\alpha,\beta).$$
The so-called dual problem is as the following form:
$$\max_{\alpha,\beta:\alpha_i\geq0}\theta_{\mathcal{D}}(\alpha, \beta)=\max_{\alpha,\beta:\alpha_i\geq0}\min_w\mathcal{L}(w,\alpha,\beta).$$
The optimal values of the primal problem and the dual problem are denoted by $p^*$ and $d^*.$
It is apparent that 
$$ d^*=\max_{\alpha,\beta:\alpha_i\geq0}\min_w\mathcal{L}(w,\alpha,\beta)\leq \min_{w}\max_{\alpha, \beta:\alpha_i\geq0} \mathcal{L(w,\alpha,\beta)}=p^*.$$
Suppose $f$ and $g_i$ 's are convex, and $h_i$'s are affine. Moreover, $g_i$'s are feasible. Under these conditions we have $p^*=d^*$, making it possible for us to solve the dual problem instead of the primal problem. Therefore, there must exist $w^*, \alpha^*, \beta^*$ such that $w^*$ is the solution to the primal problem and $\alpha^*$ and $\beta^*$ are the solution to the dual problem. So $p^*=d^*=\mathcal{L}(w^*, \alpha^*, \beta^*)$.
More importantly, $w^*$, $\alpha^*$ and $\beta^*$ satisfy the following conditions.
#### Karush-Kuhn-Tucker (KKT) conditions
$$\begin{align*}
\frac{\partial}{\partial w_i}\mathcal{L}(w^*,\alpha^*, \beta^*)&=0,\ \ i=1, 2,\dots ,d\\\\
\frac{\partial}{\partial \beta_i}\mathcal{L}(w^*,\alpha^*, \beta^*)&=0,\ \ i=1, 2,\dots ,l\\\\
\alpha_{i}^*g_i(w_i^*)&=0,\ \ i=1,2,\dots ,k\\\\
\alpha_i^*&\geq0, \ \ i=1,2,\dots ,k\\\\
g_i(w^*)&\leq0,\ \ i=1,2,\dots ,k
\end{align*}$$
Conversly if some $w^*$, $\alpha^*$ and $\beta^*$ satisfy the KKT conditions, then it is also a solution to the primal or the dual problem.
### Kernel methods
A kernel function $K(x,z)$ is a map: $\mathcal{X}\times\mathcal{X}\rightarrow\mathbb{R}$ satisfying $K(x,z)=\langle \phi(x), \phi(z)\rangle$   for any $x, z\in \mathcal{X}.$ $\phi$ is a feature map.

It is a common idea that we can transform the training instances by applying feature maps to achieve better performance. But if we do transform the vectors of the training set, the computational complexity of the training would probably increase dramatically since the dimension of the transformed vectors can be unexpectedly large. But kernels can make the whole process much more computationally efficient. 

If we apply the feature map $\phi$ to the training instances, 
then the dual problem will contain the inner product $\langle \phi(x^{(i)}),\phi( x^{(j)})\rangle.$ We can replace this inner product of transformed vectors simply by the kernel corresponding to the feature map $\phi.$
So, we don’t actually need to transform the training instances. The transformation is implicitly represented by the kernel. The result will be the same as if we had gone through the trouble of transforming the training set then fitting a linear algorithm.
#### Commmon kernels
* Linear: $K(x,z)=x^{\mathrm T}z.$
* Polynomial: $K(x,z)=(x^{\mathrm{T}}z+1)^p.$
* Gaussian: $ K(x,z)=\exp\left(-\cfrac{\|x-z\|^2}{2\sigma^2}\right).$
#### Mercer's theorem
Suppose $K$ is a map: $\mathcal{X}\times\mathcal{X}\rightarrow\mathbb{R}$. Then $K$ is a valid kernel if and only if the kernel matrix of any $\lbrace x^{(1)},\dots,x^{(n)}\rbrace$ is symmetric positive semi-definite.