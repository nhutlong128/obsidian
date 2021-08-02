##### Vector Subspace definition
- Let V = (V, +, ·) be a [[Vector Space]] and U ⊆ V, U 6= ∅. 
- Then U = (U, +, ·) is called [[Vector Subspace]] of V (or vector subspace linear subspace) if U is a [[Vector Space]] with the [[Vector Space]] operations + linear subspace and · restricted to U ×U and R×U. 
- We write U ⊆ V to denote a subspace U of V .

![[Pasted image 20210709234423.png]]

##### Vector Subspace determination
- To determine whether (U, +, ·) is a subspace of V we still do need to show
	- U != ∅, in particular: 0 ∈ U
	- Closure of U: 
		- a. With respect to the outer operation: ∀λ ∈ R ∀x ∈ U : λx ∈ U. 
		- b. With respect to the inner operation: ∀x, y ∈ U : x + y ∈ U

##### Image and Kernel
- For Φ : V → W, we define
	- [[Kernel (Null Space)]] ker(Φ) = Φ^(−1)(0_W )
	- [[Image (Range)]] Im(Φ) = Φ(V )
![[Pasted image 20210710222034.png]]

##### Orthogonal Complement
- Consider a D-dimensional [[Vector Space]] V and an M-dimensional [[Vector Subspace]] U ⊆ V . 
- Then its [[Orthogonal Complement]] U^T ⊥ is a (D−M)-dimensional [[Vector Subspace]] of V and contains all vectors in V that are orthogonal to every vector in U. 
- Furthermore, U^T ∩ U = {0} so that any vector x ∈ V can be decomposed into
- ![[Pasted image 20210711154148.png]]