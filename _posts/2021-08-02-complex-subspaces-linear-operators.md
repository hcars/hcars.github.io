---
layout: default
title: Complex Subspaces and Invariance Under Linear Operators
usemathjax: true

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

Suppose $$ u \in U $$. $$ \implies Tu = T(u) = Tu - \lambda u  + \lambda u = (T - \lambda I)u + \lambda u).

$$(T- \lambda I) u \in range(T- \lambda I) \implies (T - lambda I ) u \in U $$.

$$ \lambda u \in U $$ because $$ range(T - \lambda I) $$ is vector space and, thus, closed under scalar multiplication. 

Therefore, $$ T(u) \in U $$.

$$ \implies T_{|U} \in \mathcal{L}(U) $$.


$$U$$ is a subspace of $$V$$ which is finite dimensional. $$ \implies \exists u_{1},...,u_{j} \in U \subset V$$ such that $$ (u_{1},...,u_{j}) $$ is a basis of $$U$$. $$ T - \lambda I $$ is not surjective because all eigenvectors are in $$ null( T - \lambda I) $$, so $$ dimU < dimV $$. Thus, by assumption,

$$ \forall i \leq j, \exists (u_{k_{1}, ..., 
