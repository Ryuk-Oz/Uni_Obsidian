
Continuiamo lo studio dell'oscillatore armonico usando il metodo algebrico.
Occupiamoci dello studio delle funzioni d'onda.
Sappiamo cosa vogliamo calcolare:
$$
	\psi_{n}(x)=\braket{ x | n }   
$$
Normalizziamo gli stati $\ket{n}$.
$$
	\ket{0} : a\ket{0} =0, \quad \ket{1} = N_{1} a^{\dagger} \ket{0}  
$$
$$
	\braket{ 1 | 1 } =1= N_{1} \bra{1} a^{\dagger}\ket{0} =N_{1} \sqrt{ 1}\implies N_{1}=1 
$$
Studiamo gli stati successivi:
$$
	\ket{2} = N_{2} (a^{\dagger})^2 \ket{0} 
$$
Imponiamo la normalizzazione:
$$
	1=\braket{ 2 | 2 } = N_{2} \bra{2} (a^{\dagger})^2\ket{0} =N_{2} \bra{2} a^{\dagger}\ket{1} \bra{1} a^{\dagger}\ket{0} =N_{2} \sqrt{ 2 }\sqrt{ 1 }\implies N_{2}=\frac{1}{\sqrt{ 2\cdot{1} }} 
$$
Generalizzando al caso $n$-esimo troviamo:
$$
	N_{n}=\frac{1}{\sqrt{ n! }}
$$
Dunque:
$$
	\ket{n} = \frac{(a^{\dagger})^n}{\sqrt{ n! }} \ket{0} 
$$
Lo stato $\ket{0}$ è normalizzato per definizione.

Ricaviamo ora le funzioni d'onda, partendo dallo stato fondamentale.
$$
	a\ket{0} =0 \implies (p-im\omega x)\ket{0} =0
$$
$$
	\begin{aligned}
	0&=\bra{x} p-im\omega x\ket{0}=\int dy\, \bra{x} p \ket{y} \braket{ y | 0 }-im\omega x\underbrace{\braket{ x | 0 } }_{\psi_{0}(x)}\\
	&=\int dy\, \delta(x-y)\left( -i\hbar \frac{d}{dy} \right) \psi_{0}(y)-im\omega x \psi_{0}(x) =\left( -i\hbar \frac{d}{dx} \right) \psi_{0}(x)-im\omega x \psi_{0}(x)=0
	\end{aligned}
$$
Mi sono ricondotto ad un'equazione differenziale banale.
$$
	\frac{d\psi_{0}(x)}{dx}= -\frac{m\omega}{\hbar} x\psi_{0}(x)\implies \psi_{0}(x)=Ne^{ -1/2\; \frac{m\omega}{\hbar} x^2 }
$$
Chiamando $\sqrt{ \frac{m\omega}{\hbar} }=\alpha$ e normalizzando otteniamo:
$$
	\psi_{0}(x)= \sqrt{ \frac{\alpha}{\sqrt{ \pi }} } e^{  -1/2 \; \alpha^2 x^2}
$$
A questo punto troviamo $\psi_{n}$:
$$
	\psi_{n}=\braket{ x | n } = \frac{1}{\sqrt{ n! }} \frac{1}{(2m\hbar \omega)^{n/2}}\left( -i\hbar \frac{d}{dx}+im\omega x \right)^n \psi_{0}(x)
$$
Definisco $\xi=\alpha x=\sqrt{ \frac{m\omega}{\hbar} }x$.
$$
	\begin{aligned}
	\psi_{n}(\xi)&= \frac{1}{\sqrt{ n! }} \frac{1}{(2m\hbar \omega)^{n/2}}\left( -i\hbar \sqrt{ \frac{m\omega}{\hbar} } \frac{d}{d\xi}+im\omega \sqrt{ \frac{\hbar}{m\omega} }\xi \right)^n \psi_{0}(\xi)\\
	&=\sqrt{ \frac{\alpha}{2^n n! \sqrt{ \pi }} }(-i)^{n} \left( \frac{d}{d\xi}-\xi \right)^n e^{ -1/2\; \xi^2 }
	\end{aligned}
$$
Questa è un'altra versione della formula di Rodriguez! $\implies$ escono i polinomi di Hermite
**OSS**:
$$
	\left( \frac{d}{d\xi}-\xi \right)^n f(\xi) = \left( e^{ 1/2 \; \xi^2 } \frac{d^n}{d\xi^n} e^{ -1/2 \; \xi^2 } \right) f(\xi)
$$
Si verifica per induzione.

Sostituendo nel risultato di prima troviamo:
$$
	\psi_{n}(\xi)=N_{n} i^n e^{ -1/2\; \xi^2 }\left[ (-1)^n e^{ \xi^2 } \frac{d^n}{d\xi^n} e^{ -\xi^2 } \right] = i^n \psi_{n}^{\text{ricavati da Shrö}}(\alpha x)
$$
Abbiamo ritrovato le stesse funzioni d'onda che si otterrebbero con l'equazione di Shrödinger, moltiplicati per una fase $(i)^n$ ...MA... non ci interessa perchè sappiamo che gli stati sono gli stessi a meno di una fase e di un fattore di scala.


### Viaggi magico verso la MQ in 3-D

#### Il momento angolare in MQ

**Algebra del momento angolare:**

In meccanica classico studiamo il momento angolare come:
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
VERIFICA USANDO LE PROPRIETà DEI COMMUTATORI IN MODO ESPLICITO.
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
Ne concludiamo che $L_{x},L_{y},L_{z}$ non sono compatibili, dunque il nostro ICOC (in un problema in cui l'unica osservabile è il momento angolare) sarà:
$$
	\{ L^2,L_{z} \}
$$

**Derivazione algebrica del momento angolare**

Ricaviamo l'operatore momento angolare partendo solo da queste probabilità algebriche.
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
$J_{\pm}$ sono operatori di innalazamento e abbassamento per $m$. Vediamo come
$$
	J^2(J_{\pm}\ket{j,m} )=J_{\pm}(J^2 \ket{j,m} )=j(j+1)(J_{\pm}\ket{j,m} )
$$
lo stato $J_{\pm}\ket{j,m}$ è autostato di $J^2\in j(j+1)$
$$
	J_{z}(J_{\pm}\ket{j,m} )= (J_{\pm}J_{z}\pm J_{\pm})\ket{j,m} =(m\pm1)(J_{\pm}\ket{j,m} )
$$
lo stato $J_{\pm}\ket{j,m}$ è autostato di $J_{z}\in m\pm{1}$. Sembra che $m$ debba andare a passi interi.
Dunque:
$$
	J_{\pm}\ket{j,m} \propto \ket{j,m\pm1} 
$$
Poichè, trovandoci in un icoc, non c'è ulteriore degenerazione, dunque esiste un solo stato associato all'autovalore $m+1$. Per convenzione chiamiamo questo stato $\ket{m+1}$ e in un certo senso stiamo "ordinando" la nostra base.
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
	J_{+}J_{-}=J^2-J_{z^2}+J_{z}
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
2. Il caso negativo reistituisce:
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
L'azione di $J_{\pm}$ su $\ket{j,m}$ DEVE TERMINARE, quindi nei limiti dell'intervallo di esistenza di $m$, $[-j,j]$,  devo avere $N_{jm}^\pm=0$. Infatti:
$$
	N^-_{j,-j}=\sqrt{ j(j+1)-(-j)(-j-1) }=0
$$
$$
	N^+_{j,j}=\sqrt{ j(j+1)-j(j+1) }=0
$$
Se anzichè scegliere come autovalori $j(j+1)$ avessi scelto $\lambda$ generico, sarei riuscito a ritrovare $j(j+1)$ imponendo la fine dell'azione di $J_{\pm}$.
Quindi devono esistere gli stati $\{ \ket{j,j}, \; \ket{j,-j} \}$, cioè i valori estremi di $m$ sono raggiunti.
Questo significa che partendo da $m=-j$ devo arrivare a $m=+j$ facendo passi interi $\implies 2j \in \mathbb{N}$

PROVA A RIFARE TUTTO CON $\lambda$ generico al posto di $j(j-1)$ e vedi cosa esce.

Alla fine di tutto arriviamo a drie:
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


