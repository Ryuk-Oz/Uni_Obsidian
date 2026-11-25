
   $$
	\sigma_{x}=\begin{pmatrix}
	0 & 1 \\
	1 & 0
	\end{pmatrix} \quad \sigma_{y}=\begin{pmatrix}
	0 & -i \\
	i & 0 
	\end{pmatrix} \quad \sigma_{z} = \begin{pmatrix}
	1 & 0 \\
	0 & -1
	\end{pmatrix}
   $$
   Queste matrici sono tali che:
   $\sigma^2_{i}= \mathbb{1}_{2\times{2}}$. Allora, definendo le nuove matrici: $S_{i}=\frac{\hbar}{2} \sigma_{i}$ troviamo:
   $$
	[S_{i},S_{j}]=i\hbar\varepsilon_{ijk}S_{k}
   $$
$$
	S^2 = S_{x}^2+S_{y}^2+S_{z}^2=\frac{3}{4} \hbar^2 \mathbb{1}_{2\times 2}
   $$
   Abbiamo studio le matrici di Pauli nella base in cui $S_{z}=\frac{\hbar}{2} \sigma_{z}$ è diagonale.
   Possiamo estenderle in 3 dimensioni (e troviamo le rotazioni):
$$
	L_{x}=i\hbar\begin{pmatrix}
	0 & 0 & 0 \\
	0 & 0 & -1 \\
	0 & 1 & 0
	\end{pmatrix}
	\quad L_{y}=i\hbar \begin{pmatrix}
	0 & 0 & 1 \\
	0 & 0 & 0 \\
	-1 & 0 & 0
	\end{pmatrix} \quad L_{z}=i\hbar \begin{pmatrix}
	0 & -1 & 0 \\
	1 & 0 & 0 \\
	0 & 0 & 0
	\end{pmatrix}
$$
   e troviamo:
$$
	[L_{i},L_{j}]= i\hbar \varepsilon_{ijk} L_{k}
   $$
$$
	L^2= 2\hbar \mathbb{1}
   $$
Questo apre all'idea di funzioni d'onda vettoriali, con più di una componente, sulle quali agiscono queste matrici anzichè gli operatori differenziali.
Per valori di $j,m$ impareremo a conoscere pertanto oggetti di natura diversa.

**OSS:** le matrici di Pauli 2-d, a differenza di quelle 3-d, sono matrici complesse, pertanto acquisiscono senso soltanto nell'ambito della meccanica quantistica.

**Argomento associato:** [[Autofunzioni del momento angolare, armoniche sferiche]]