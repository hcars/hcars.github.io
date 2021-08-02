---
layout: default
title: Complex Subspaces and Invariance Under Linear Operators
usemathjax: true
tags: Math Linear-Algebra 
---


# Assertion

Suppose $$V$$ is a finite-dimensional vector space over $$\mathbf{C}$$ with $$dimV = n $$. Suppose $$ T \in \mathcal{L}(V) $$.
Therefore, $$ \forall i \leq n, \exists U \subset V $$ such that $$ dimU = i $$ and $$U$$ is invariant under $$T$$.

## Proof 

Suppose $$V$$ is a finite-dimensional vector space over $$\mathbf{C}$$ with $$dimV = n $$. Suppose $$ T \in \mathcal{L}(V) $$.

By Induction,

### Base Case: 
Suppose $$dimV = 1 $$. $$ V \subset V $$ and $$ V $$ is invariant under $$T$$ by $$ T \in \mathcal{L}(V) $$. 
This demonstrates the conclusion for the case $$dimV = 1 $$.

### Inductive Case:
Assume  $$ \forall V$$ such that $$ dimV \leq n $$ the conclusion holds.
Suppose $$V$$ is a finite dimensional vector space over $$ \mathbf{C}$$ such that $$ dimV = n + 1 $$, and $$T \in \mathcal{L}(V) $$. 
Because $$T \in \mathcal{L}(V) $$ and $$V$$ is a complex vector space, $$\exists \lambda \in \mathcal{C}$$ such that $$\lambda$$ is an eigenvalue of $$V$$.

Let $$U = range(T - \lambda I) $$

Suppose $$ u \in U $$. $$ \implies Tu = T(u) = Tu - \lambda u  + \lambda u = (T - \lambda I)u + \lambda u).$$

$$(T- \lambda I) u \in range(T- \lambda I) \implies (T - \lambda I ) u \in U $$.

$$ \lambda u \in U $$ because $$ range(T - \lambda I) $$ is vector space and, thus, closed under scalar multiplication. 

Therefore, $$ T(u) \in U $$.

$$ \implies T_{\|U} \in \mathcal{L}(U) $$.


$$U$$ is a subspace of $$V$$ which is finite dimensional. $$ \implies \exists u_{1},...,u_{j} \in U \subset V$$ such that $$ (u_{1},...,u_{j}) $$ is a basis of $$U$$. $$ T - \lambda I $$ is not surjective because all eigenvectors are in $$ null( T - \lambda I) $$, so $$ dimU < dimV $$. Thus, by assumption,

$$ \forall i \leq j, \exists (u_{k_{1}}, ..., u_{k_{i}})$$ that forms an invariant subspace of $$U$$. Thus, for $$i \leq j $$, V has an invariant subspace of dimension $$i$$. 

$$dimU < dimV \implies \exists (v_{1}, ... v_{m}) \in V - U $$ such that $$ (u_{1},...,u_{j},v_{1},...,v_{m} ) $$ is a basis of V. 

Let $$ x \in (u_{1}, ... , u_{j}, v_{1}, ... v_{t}), k \leq m $$.

$$ \implies \exists a_{1},...,a_{j},b_{1},...,b_{t} \in \mathcal{C} $$ such that $$ x = a_{1}u_{1} + ... + a_{j}u_{j} + b_{1}v_{1} + ... + b_{t}v_{t} $$.

Let $$ t \leq m $$.

$$ Tv_{t} = Tv_{t} - \lambda v_{t} + \lambda v_{t} = (T - \lambda I ) v_{t} + \lambda v_{t} $$.

Thus, $$ Tv_{t} \in span(u_{1}, ..., u_{j}, v{t} ) $$.

Thus, $$ Tx = T(a_{1}u_{1} + ... + a{j}u_{j}) + b_{1}Tv_{1} + ... + b_{t}Tv_{t} $$ .


$$ T(a_{1}u_{1} + ... + a{j}u_{j}) \in span( T(u_{1} + ... ,u_{j}) $$ by $$U$$ invariant under $$T$$.

$$ b_{1}Tv_{1} \in span(u_{1}, ..., u_{j}, v_{1}) $$ by $$Tv_{1} \in span(u_{1}, ..., u_{j}, v_{1}) $$
....
....
$$ b_{1}Tv_{t} \in span(u_{1}, ..., u_{j}, v_{1}, ..., v_{t}) $$ by $$Tv_{t} \in span(u_{1}, ..., u_{j}, v_{1}, ... , v_{t}) $$


Thus, $$Tx \in span(u_{1},...,u_{j},v_{1},...,v_{t}) $$, so $$ (u_{1},...,u_{j},v_{1},...,v_{t}) $$ is invariant under $$T$$ for $$ t \leq m $$.

Therefore, $$V$$ is has an invariant subspace for all $$i \leq n + 1 $$.


Q.E.D.
