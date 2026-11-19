
**Utile:** [[Algebra del momento angolare]]
**Simile:** [[Azione degli operatori gradino sugli autostati dell'Hamiltoniana]]

**OSS:** sia gli operatori gradino nel caso dell'oscillatore armonico che in quello del momento angolare corrispondono a una rotazione (in un caso sullo spazio delle fasi, in un altro sul piano $x$, $y$).

Ricaviamo l'operatore momento angolare partendo solo da queste proprietà algebriche.
Ci mettiamo in un sistema di misura in cui $\hbar=1$.
$$
	[J_{i},J_{j}]=i \varepsilon_{ijk} J_{k}
$$
$$
	[J^2, J_{i}]=0
$$
e $J_{i}$ operatori autoaggiunti su uno spazio di Hilbert $\mathcal{H}$.
Il mio ICOC è $\{ J^2, J_{z}\}$, devo trovare una base.
$$
	\begin{cases}
	J^2 \ket{j,m} =j(j+1)\ket{j,m}  \\
	J_{z} \ket{j,m} =m \ket{j,m} 
	\end{cases}
$$
con $j(j+1) \in \mathbb{R}$, $m\in \mathbb{R}$. 
$j(j+1)\geq0$, infatti:
$$
	\begin{aligned}
	\bra{j,m} J^2\ket{j,m} &=j(j+1)\\
	&= \sum^3_{i=1} \bra{j,m} J_{i}^2\ket{j,m}=\sum^3_{i=1} \bra{j,m} J^{\dagger}J\ket{j,m} \\
	&=\sum^3_{i=1}\lVert J_{i}\ket{j,m}  \rVert \geq 0
	\end{aligned}
$$
Ho due possibilità, $j\geq0$ e $j\leq-1$. Devo studiare due casi separati? No, qualunque scelta io faccia è analoga, basta usare la trasformazione $j\leftrightarrow-j-1$ che lascia invariato $j(j+1)$.
Per comodità scelgo $j\geq 0$.

Definisco 2 operatori (che salgono e scendono):
$$
	J_{\pm}\equiv J_{x}\pm iJ_{y}\implies J_{-}=J^{\dagger}_{+}
$$
L'algebra diventa:
$$
	[J^2, J_{\pm}]=0
$$
$$
	[J_{+},J_{-}]=[J_{x}+iJ_{y}, J_{x}-iJ_{y}]=(-i)(iJ_{z})+i(-iJ_{z})=2J_{z}
$$
$$
	[J_{z},J_{\pm}]=[J_{z},J_{x}\pm iJ_{y}]=iJ_{y}\pm i(-iJ_{x})=\pm J_{x}+iJ_{y}=\pm J_{\pm}
$$
$J_{\pm}$ sono operatori di innalazamento e abbassamento per $m$. Vediamo come:
$$
	J^2(J_{\pm}\ket{j,m} )=J_{\pm}(J^2 \ket{j,m} )=j(j+1)(J_{\pm}\ket{j,m} )
$$
lo stato $J_{\pm}\ket{j,m}$ è autostato di $J^2\in j(j+1)$
$$
	J_{z}(J_{\pm}\ket{j,m} )= (J_{\pm}J_{z}\pm J_{\pm})\ket{j,m} =(m\pm1)(J_{\pm}\ket{j,m} )
$$
lo stato $J_{\pm}\ket{j,m}$ è autostato di $J_{z}\in m\pm{1}$. A questo punto ha senso chiedersi se $m$ vada a passi interi o se esistano autovalori intermedi.
Poichè, trovandoci in un icoc, non c'è ulteriore degenerazione, dunque esiste un solo stato associato all'autovalore $m+1$, possiamo dire che:
$$
	J_{\pm}\ket{j,m} \propto \ket{j,m\pm1} 
$$
Per convenzione chiamiamo questo stato $\ket{m+1}$ (potevo anche chiamarlo $\ket{\text{pippo}}$, ma "ordinare" la nostra base è comodo).
$$
	\implies J_{\pm}\ket{j,m} =N^\pm_{j,m}\ket{j,m\pm1} 
$$
posso calcolare questa costante.
$$
	\bra{j,m} J_{\mp}J_{\pm}\ket{j,m} =|N^\pm_{j,m}|^2
$$
prendiamo uno tra $J_{-}$ e $J_{+}$.
$$
	J_{-}J_{+}= (J_{x}-iJ_{y})(J_{x}+iJ_{y})=J_{x}^2+J_{y}^2+i[J_{x},J_{y}]=J^2-J_{z}^2-J_{z}
$$
Il caso opposto sarà:
$$
	J_{+}J_{-}=J^2-J_{z}^2+J_{z}
$$
Dunque:
$$
	|N_{jm}^\pm|^2 = j(j+1)-m(m\pm{1})\geq 0
$$
è un sistema di 2 equazioni quadratiche in $j,m$.
1. Studio il caso positivo, $j(j+1)-m(m+1)\geq 0$.
   $m^2+m-j(j+1)\leq0$, allora:
$$
	m=-\frac{1}{2} \pm \frac{1}{2}\sqrt{ 1+4j(j+1) }=-\frac{1}{2}\pm \frac{2j+1}{2}=\begin{cases}
	j \\
	-j-1
	\end{cases}
$$
   $\implies -j-1 \leq m\leq j$
2. Il caso negativo restituisce:
   $$
	m=\begin{cases}
	j+1 \\
	-j
	\end{cases}\implies-j\leq m\leq j+1
   $$
Entrambi i casi devono essere soddisfatti contemporaneamente, dunque:
$$
	-j\leq m\leq j
$$
Questo ci dice che $|L_{z}|^2 \leq |L|^2$.
L'azione di $J_{\pm}$ su $\ket{j,m}$ DEVE TERMINARE e $m$ DEVE RAGGIUNGERE GLI ESTREMI, quindi nei limiti dell'intervallo di esistenza di $m$, $[-j,j]$,  devo avere $N_{jm}^\pm=0$. Infatti:
$$
	N^-_{j,-j}=\sqrt{ j(j+1)-(-j)(-j-1) }=0
$$
$$
	N^+_{j,j}=\sqrt{ j(j+1)-j(j+1) }=0
$$
Quindi devono esistere gli stati $\{ \ket{j,j}, \; \ket{j,-j} \}$, cioè i valori estremi di $m$ sono raggiunti.
Questo significa che partendo da $m=-j$ devo arrivare a $m=+j$ facendo passi interi $\implies 2j \in \mathbb{N}$

Se anzichè scegliere come autovalori $j(j+1)$ avessi scelto $\lambda$ generico, sarei riuscito a ritrovare gli stessi risultati scritti in forma meno bella.
Nello specifico, troverei:
$$
	-\left( \frac{\sqrt{ 1+4\lambda }-1}{2} \right)\leq m\leq \frac{\sqrt{ 1+4\lambda }-1}{2}
$$
In modo più difficile da qua si vede sempre che $|L_{z}|^2\leq |L|^2$, e troviamo che l'azione di $j$ termina ugualmente.
Infine per ritrovare $\lambda=j(j+1)$ basta imporre:
$$
	\frac{\sqrt{ 1+4\lambda }-1}{2}=j
$$
(Dove ho scelto di chiamarla $j$ in maniera arbitraria).

Alla fine di tutto arriviamo a dire:
$$
	\begin{cases}
	J^2 \ket{j,m} = j(j+1)\ket{j,m}  \\
	J_{z}\ket{j,m} =m \ket{j,m} 
	\end{cases}
$$
con:
$$
	\begin{cases}
	j=0, \frac{1}{2}, 1, \frac{3}{2}, 2, \dots \\
	j\leq m \leq j
	\end{cases}
$$
$j=0\implies J^2=0, \;m=0, \, J_{z}=0$
$j= \frac{1}{2} \implies J^2 =\frac{3}{4}\hbar^2, \; m\in \left\{  -\frac{1}{2}, \frac{1}{2}  \right\}, \; J_{z}=\pm \frac{\hbar}{2}$
$j=1\implies J^2= 2\hbar^2,\; m \in \{ -1,0,1 \}, \; J_{z}=0, \pm \hbar$
in generale $m$ ha $2j+1$ valori.
Il momento angolare è quantizzato, non è un vettore in senso stratto ma un vettore di operatori.

Reintroducendo $\hbar$ abbiamo:
$$
	\begin{cases}
	J^2\ket{j,m} =\hbar^2\, j(j+1)\ket{j,m} \\
	J_{z}\ket{j,m} =\hbar \, m\ket{j,m} 
	\end{cases}
$$

**Lezione Associata:** [[8. Momento angolare in meccanica quantistica]]