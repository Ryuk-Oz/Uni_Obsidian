**Utile:** [[Insiemi completi di osservabili compatibili]]

In meccanica classica il momento angolare è uno pseudovettore, come possiamo vedere dalla sua definizione:
$$
	\begin{cases}
	\vec{L} = \vec{r} \wedge \vec{p} \\
	L_{i} = \sum^3_{j,k=1} \varepsilon _{ijk} x_{j}p_{k}
	\end{cases}
$$
In MQ questo diventa:
$$
	\begin{cases}
	\vec{L}=-i\hbar \vec{r}\wedge \vec{\nabla} \\
	L_{i}=-i\hbar \sum^3_{j,k=1} \varepsilon_{ijk} x_{j} \frac{ \partial  }{ \partial x_{k} } 
	\end{cases}
$$
Scriviamo esplicitamente le 3 componenti:
$$
	\begin{cases}
	L_{x}=yp_{x}-xp_{y} \\
	L_{y}=zp_{x}-xp_{z} \\
	L_{z}=xp_{y}-yp_{x}
	\end{cases} \implies
	\begin{cases}
	-i\hbar \left( y \frac{ \partial  }{ \partial z } -z \frac{ \partial  }{ \partial y }  \right) \\
	-i\hbar\left( z\frac{ \partial  }{ \partial x } -x\frac{ \partial  }{ \partial z }  \right) \\
	-i\hbar \left( x\frac{ \partial  }{ \partial y}-y \frac{ \partial  }{ \partial x }  \right)
	\end{cases}
$$
In MQ questi operatori non commutano:
$$
	[L_{x},L_{y}]=[yp_{z}-zp_{y},zp_{x}-xp_{z}]=y[p_{z},z]p_{x}+x[z,p_{z}]p_{y}=i\hbar(xp_{y}-yp_{x})=i\hbar L_{z}
$$
Analogamente, ciclando in senso orario abbiamo:
$$
	\begin{aligned}
	&[L_{z},L_{x}]=i\hbar L_{y}\\
	&[L_{y},L_{z}]=i\hbar L_{x}
	\end{aligned}
$$
In generale.
$$
	[L_{i},L_{j}]=i\hbar \varepsilon_{ijk}L_{k}
$$
Non devo alzare l'indice perchè la metrica non relativistica è l'identità.
Definiamo il momento quadro.
$$
	L^2 = |\vec{L}|^2 = L_{x}^2+L_{y}^2+L_{z}^2
$$
Commuta con il momento angolare?
$$
	\begin{aligned}
	[L^2, L_{z}]&=[L_{x}^2+L_{y}^2, L_{z}]=L_{x}[L_{x},L_{z}]+[L_{x},L_{z}]L_{x}+ L_{y}[L_{y},L_{z}]+[L_{y},L_{z}]L_{y}\\
	&=-i\hbar L_{x}L_{y}-i\hbar L_{y}L_{z}+i\hbar L_{y}L_{x}+i\hbar L_{x}L_{y}=0
	\end{aligned}
$$
Le tre componenti del momento angolare NON commutano tra loro ma commutano con il momento quadro.
$$
	[L^2,L_{i}]=0
$$
Ne concludiamo che $L_{x},L_{y},L_{z}$ non sono compatibili, dunque il nostro ICOC (in un problema in cui l'unica osservabile è il momento angolare) sarà qualcosa del tipo:
$$
	\{ L^2,L_{z} \}
$$
(Perchè $L^2$ e $L_{z}$ sono diagonalizzabili simultaneamente),
Dove $L_{z}$ viene scelto in maniera arbitraria.

**Lezione Associata:** [[8. Momento angolare in meccanica quantistica]]