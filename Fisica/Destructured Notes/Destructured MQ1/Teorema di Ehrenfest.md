
Considero $Q$ osservabile, dunque: $Q=Q^{\dagger}$, $\ket{\alpha}\in \mathcal{H}$.
$$
	\begin{aligned}
	\frac{d}{dt}\bra{\alpha} Q\ket{\alpha} =\left( \frac{ \partial  }{ \partial t }  \bra{\alpha}  \right) Q \ket{\alpha} + \bra{\alpha} \frac{ \partial Q }{ \partial t }  \ket{\alpha} +\bra{\alpha}Q \left( \frac{ \partial  }{ \partial t }  \ket{\alpha} \right) 
	\end{aligned}
$$
A queto punto sfrutto l'eq. di shrodinger:
$$
	i\hbar \frac{d}{dt} \ket{\alpha}  = H \ket{\alpha} 
$$
e:
$$
	-i\hbar \frac{d}{dt} \bra{\alpha}  = \bra{\alpha} H
$$
Dunque:
$$
	\begin{aligned}
	\frac{d}{dt} \langle Q \rangle _{\alpha} = \frac{i}{\hbar} \bra{\alpha} HQ \ket{\alpha} + \langle \frac{ \partial Q }{ \partial t }  \rangle _{\alpha}- \frac{i}{\hbar} \bra{\alpha} QH\ket{\alpha} = \langle  \frac{ \partial Q }{ \partial t }  \rangle _{\alpha} +\frac{i}{\hbar} \langle [H,Q] \rangle _{\alpha}
	\end{aligned}
$$
 Dunque:
 $$
	\frac{d}{dt} \langle Q \rangle _{\alpha} = \langle  \frac{ \partial Q }{ \partial t }  \rangle _{\alpha} +\frac{i}{\hbar} \langle [H,Q] \rangle _{\alpha}
 $$
 Che è totalmente analogo a quello che trovo in meccanica classica:
$$
	\frac{dA}{dt} = \frac{ \partial A }{ \partial t } + \{ A,H \}_{\text{pp}}
 $$
 Ho quindi una corrispondenza biunivoca tra le parentesi di poisson in meccanica classica e il commutatore in meccanica quantistica.
Si può ricostruire tutta la meccanica quantistica proprio a partire da questa equivalenza (è ciò che fa Dirac nei sui principi di meccanica Quantistica).

**Lezione Associata**: [[6.Principi Fondativi della meccanica quantistica]]