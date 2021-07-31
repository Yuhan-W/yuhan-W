---
title: The Singular Value Decomposition (SVD)
subtitle: Linear algebra

# Summary for listings and search engines
summary: Welcome 👋 We know that first impressions are important, so we've populated your new site with some initial content to help you get familiar with everything in no time.

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
  caption: 'Figure 1'
  focal_point: ""
  placement: 2
  preview_only: false

authors:
- admin

tags:
- Matrix decomposition

categories:
- Math
- Linear Algebra
---

The singular value decomposition (SVD) is a factorization of any $m\times n$ matrix and it can be seen as a generalization of eigendecompostion which can only be applied to diagonalizable matrices. And the SVD also has multiple applications in different fields. This article explains the basic theory of the SVD and its geometric interpretation.

## The Matrices in the SVD
There is an important fact that every real symmetric matrix $S$ has the factorization: $S = Q\Lambda Q^{-1}=Q\Lambda Q^\mathrm{T}$ with orthonormal eigenvectors in $Q$ and real eigenvalues in $\Lambda$. Suppose that $A$ is an $m\times n$ matrix, then $A^{\mathrm{T}}A$ and $AA^{\mathrm{T}}$ are symmetric matrices. So it is not difficult to diagonalize $A^{\mathrm{T}}A$ or $AA^{\mathrm{T}}$ using a matrix with a set of orthonormal eigenvectors in its columns. Suppose that $\boldsymbol v_{1},…\boldsymbol v_{n}$ are orthonormal eigenvectors of $ A^{\rm{T}}A$ and $ \lambda_1,…\lambda_n$ are eigenvalues of $ A^{\rm{T}}A$ . Then for   $1\leq i\leq n$, we have

$$\begin{align*} ||A\boldsymbol v_i||^2 &=(A\boldsymbol v_i)^{\rm{T}}A\boldsymbol v_i =\boldsymbol v_i^{\rm{T}}A^{\rm{T}}A\boldsymbol v_i \\ &=\boldsymbol v_i^{\rm{T}}(\lambda_i\boldsymbol v_i)=\lambda_i\geq0 \end{align*}$$

It is evident that the eigenvalues of $AA^{\rm{T}}$ equal the eigenvalues of $A^{\rm{T}}A$ . Similarly, we can find another orthogonal set $\boldsymbol u_1,…\boldsymbol u_m$ (orthonormal eigenvectors of $AA^{\rm{T}}$ ). Now, we have

$$\begin{align}A^{\rm{T}}A\boldsymbol v_i=\sigma_i^2\boldsymbol v_i\\AA^{\rm{T}}\boldsymbol u_ i=\sigma_i^2\boldsymbol u_i\end{align}$$

The $\sigma$ 's are singular values, square roots of the eigenvalues of $A^{\rm{T}}A$ and $ AA^{\rm{T}}$ . From equations(1), we can get

$$AA^{\rm{T}}(A\boldsymbol v_i)=A(A^{\rm{T}}A)\boldsymbol v_i = \sigma_i^2(A\boldsymbol v_i)$$

Since $||A\boldsymbol v_i||=\sigma_i$, it is easy to find $$\begin{align}A\boldsymbol v_i=\sigma_i\boldsymbol u_i \end{align}$$ 

Suppose that singular values $\sigma_1$ to $\sigma_r$ are positive numbers. Then the equations (3) show that
$$ A \left [ \begin{matrix} \boldsymbol v_1,&…&\boldsymbol v_r   \end{matrix} \right ] =  \left [ \begin{matrix} \boldsymbol u_1,&…&\boldsymbol u_r   \end{matrix} \right ] \left [  \begin{matrix} \sigma_1&  \\ &\ddots\\  & &\sigma_r \end{matrix} \right ]$$

or $AV_r=U_r\Sigma_r$. Now we include $n-r$ more $\boldsymbol{v}$ 's and $m-r$ more $\boldsymbol u$ 's in orthogonal matrices $V$ and $U$ .Finally, $AV_r=U_r\Sigma_r$ becomes $AV=V\Sigma$ ,i.e. $A=U\Sigma V^{\rm{T}}$.

### Theorem

Any $m\times n$ matrix $A$ has a decomposition $A=U\Sigma V^{\mathrm{T}}$ .

$U$ is an $m\times m$ orthogonal matrix.

$V$ is an $n\times n$ orthogonal matrix.

$\Sigma$ is an $m\times n$ matrix $ \left [ \begin{matrix} \Sigma_r&0 \\ 0&0\\ \end{matrix} \right ] $ , in which $\Sigma_r= \left [  \begin{matrix} \sigma_1&  \\ &\ddots\\  & &\sigma_r \end{matrix} \right ]$ .

We usually put the singular values of $A$ in descending order, $\sigma_1\geq \sigma_2\geq …\sigma_r>0$. This kind of factorization is called the singular value decomposition (SVD).

## The Geometry of the SVD
After explaining the matrices in the SVD, let's look at the SVD from a different perspective. The geometric meanings of the SVD are great intuitive interpretations of this kind of factorization. We know that every symmetric matrix $S$ has decomposition: $S = Q\Lambda Q^{-1}=Q\Lambda Q^{\rm{T}}$. This represents a transformation:(rotate)(stretch)(rotate back).

As for the singular value decomposition, any matrix can be separated into three pieces: orthogonal matrix, "diagonal" matrix, another orthogonal matrix. Let's consider a linear transformation $T: \boldsymbol x\rightarrow A \boldsymbol x$ , in which $ A\boldsymbol x=U\Sigma V^{\rm{T}}\boldsymbol x$ using SVD. The geometric meanings of this transformation is :(rotate)(stretch)(rotate). The following picture illustrates the geometry behind the SVD when matrix $A$ is a $2\times 2$ matrix.


## License

Released under the [MIT](https://github.com/wowchemy/wowchemy-hugo-modules/blob/master/LICENSE.md) license.
