- The rank of [[Matrix]] A (denoted by rk(A)) is the number of [[Linearly Independent Row]] = the number of [[Linearly Independent Column]]
- [[Matrix Rank]] properties:
	- [[Matrix Rank]] of R^mxn is [[Matrix Full Rank]] if rk(A) = min(m, n)
	- The columns of A ∈ Rm×n span a subspace U ⊆ Rm with dim(U) = rk(A). Later we will call this subspace the [[Image (Range)]]
	- For A ∈ Rm×n the subspace of solutions for Ax = 0 possesses dimension n − rk(A). Later, we will call this subspace the [[Kernel (Null Space)]]
	-  For all A ∈ Rn×n it holds that A is regular (invertible) if and only if rk(A) = n
	-  For all A ∈ Rm×n and all b ∈ Rm it holds that the linear equation system Ax = b can be solved if and only if rk(A) = rk(A|b), where A|b denotes the augmented system