
**Lezione associata:** [[1.Introduzione e concetti base di teoria della probabilità]]
___

Nel 1900 Hilbert annuncia la necessità di assiomatizzare la teoria della probabilità in quanto unico modo di definirla efficacemente (come ha fatto Euclide con la geometria). Questo viene fatto nel 1933 da Kolmogorov.

Consideriamo dunque un insieme $\Omega$ di eventi elementari (spazio degli eventi) e $I$, una famiglia di eventi contenuta in $\Omega$. Allora valgono i seguenti assiomi:
1. $I$ è un algebra di insiemi, cioè: 
   $$
   	\forall \, A,B\in I \Rightarrow \{ A \cup B, A\cap B, \bar{A}=\Omega-A \} \in I
   $$
2. $\forall \, A \in I$ associo un numero reale $P(A)\geq 0$ che chiamo "Probabilità di A"
3. $P(\Omega)=1$
4. Se $A\cap B=\emptyset$ cioè i due insiemi sono disgiunti, $\Rightarrow$ $P(A \cap B)=P(A)+P(B)$

Da questi 4 assiomi posso costruire tutta la teoria della probabilità.

#### Corollari di questi assiomi:

- $P(\bar{A})=1-P(A)$ (dimostrazione banale)
- $P(\emptyset)=0$ (dimostrazione banale)
- $0\leq P(A)\leq {1}$ (dimostrazione per assurdo)

Studiamo ora cosa succede nel caso in cui l'insieme $\Omega$ diventi continuo. 
Ad esempio $\Omega \subset \mathbb{R}$. Un elemento $A$ della famiglia $I$ diventa un intervallo continuo.
$$
	A=[a,b)
$$
![[Pasted image 20260925000239.png]]

La probabilità di $A$ è la sua misura, per definirla devo introdurre una funzione di distribuzione:
$$
	F_{X}(x) \equiv P[X\leq x] = \int^X_{-\infty}p(x)dx
$$
dove abbiamo introdotto anche una funzione densità di probabilità:
$$
	p_{X}(x)=\frac{dF_{X}}{dx}
$$
e la probabilità di $A$ diventa:
$$
	P(A)=\int^a_{b}p(x)dx
$$