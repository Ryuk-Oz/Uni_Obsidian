
VEDI SE SIA NECESSARIO AGGIUNGERE ROBE DALLE DISPENSE

OSS: l'algebra dei momenti che abbiamo visto ieri ha a che fare con il gruppo $SU(2)$ e $SO(3)$, cioè ha a che fare con le rotazioni.
Per tale motivo ha senso usare le coordinate polari sferiche.
Convenzione magne: $\varphi$ angolo azimutale, $\theta$ angolo (verticale?).
$$
	\begin{cases}
	x = r\sin \theta \cos \varphi \\
	y=r\sin \theta \sin \varphi \\
	z=r\cos \theta
	\end{cases}
$$
Con $\theta \in[0,\pi]$, $\varphi \in[0,2\pi)$.

FAI TUTTI I CONTI CON CALMA A CASA.

Dobbiamo calcolare la matrice Jacobiana della trasformazione.
$$
	\begin{cases}
	r=\sqrt{ x^2+y^2+z^2 } \\
	\varphi=\arctan \frac{x}{y} \\
	\theta=\arcsin \frac{z}{r}
	\end{cases}
$$
Anzichè usare le derivate ragioniamo con i differenziali:
$$
	\begin{cases}
	r^2=x^2+y^2+z^2 \implies r dr =xdx+ydy+zdz \\
	d\varphi = -\frac{y}{x^2+y^2}dx+\frac{x}{x^2+y^2}dy \\
	\cos \theta=\frac{z}{r}\implies-\sin \theta d\theta= -\frac{z}{r^3}(xdx+ydy+zdz)+\frac{dz}{r}
	\end{cases}
$$
dunque:
$$
	J=\begin{pmatrix}
	\frac{ \partial r }{ \partial x } = \sin \theta \cos \varphi & \frac{ \partial r }{ \partial y } = \sin \theta \sin \varphi & \frac{ \partial r }{ \partial z } =\cos \theta \\
	 \frac{ \partial \varphi }{ \partial x } =-\frac{\sin \varphi}{r\sin \theta} & \frac{ \partial \varphi }{ \partial y }= \frac{\cos \varphi}{r\sin \theta} & \frac{ \partial \varphi }{ \partial z } =0 \\
	 \frac{ \partial \theta }{ \partial x } =\frac{\cos \theta \cos \varphi}{r} & \frac{ \partial \theta }{ \partial y } =\frac{\cos \theta \sin \varphi}{r} & \frac{ \partial \theta }{ \partial z } =-\frac{\sin \theta}{r} 
	\end{pmatrix}
$$
Ora possiamo scrivere le componenti di $\vec{L}$ in coordinate sferiche.
$$
	\begin{aligned}
	L_{z}&=-i\hbar\left( x \frac{ \partial  }{ \partial y } -y\frac{ \partial  }{ \partial x }  \right)=\\
	&=-i\hbar\left[ x\left( \frac{ \partial r }{ \partial y } \frac{ \partial  }{ \partial r } +\frac{ \partial \varphi }{ \partial y } \frac{ \partial  }{ \partial \varphi } +\frac{ \partial \theta }{ \partial y } \frac{ \partial  }{ \partial y }  \right)-y\left( \frac{ \partial r }{ \partial x } \frac{ \partial  }{ \partial r } +\frac{ \partial \varphi }{ \partial x } \frac{ \partial  }{ \partial \varphi } +\frac{ \partial \theta }{ \partial x }\frac{ \partial  }{ \partial \theta }   \right) \right]\\
	&=-i\hbar\left[ r\sin \theta \cos \varphi\left( \cancel{\sin \theta \sin \varphi \frac{ \partial  }{ \partial r }} +\cancel{\frac{\cos \theta \sin \varphi}{r}\frac{ \partial  }{ \partial \theta }} +\frac{\cos \varphi}{r\sin \theta} \frac{ \partial  }{ \partial \varphi } \right) \\
	-r\sin \theta \sin \varphi \left( \cancel{\sin \theta \cos \varphi \frac{ \partial  }{ \partial r }} +\cancel{\frac{\cos \theta \cos \varphi}{r}\frac{ \partial  }{ \partial \theta }} -\frac{\sin \varphi}{r\sin \theta} \frac{ \partial  }{ \partial \varphi }  \right)\right]=\\
	&=-i\hbar \frac{ \partial  }{ \partial \varphi } 
	\end{aligned}
$$
**OSS:** $L_{z}$ assomiglia all'operatore impulso
Posso calcolare anche $L_{x}$ e $L_{y}$:
$$
	L_{x}=i\hbar \left[ \sin \varphi \frac{ \partial  }{ \partial \theta } +\frac{\cos \varphi \cos \theta}{\sin \theta} \frac{ \partial y }{ \partial \varphi }  \right]
$$
$$
	L_{y}=-i\hbar\left[ \cos \varphi \frac{ \partial  }{ \partial \theta } -\frac{\sin \varphi \cos \theta}{\sin \theta} \frac{ \partial  }{ \partial \varphi }  \right]
$$
Ma a noi non interessano questi, ci interessano piuttosto $L_{\pm}$.
$$
	L_{\pm}\equiv L_{x}\pm iL_{y}=\pm \hbar e^{ \pm i\varphi }\left[ \frac{ \partial  }{ \partial \theta } \pm i \frac{\cos \theta}{\sin \theta}\frac{ \partial  }{ \partial \varphi }  \right]
$$
Gli operatori $L_{i}$ (e quindi $L^2$) NON dipendono da $r$, allora sono autoaggiunti sullo spazio vettoriale delle funzioni monodrome a quadrato sommabili sulla SFERA $S^2$, cioè $L^2(S^2)$.
Agiscono cioè su $f(\theta,\varphi)$ tali che:
- $f(\theta,\varphi)=f(\theta,\varphi+2\pi),\; \forall \theta$, cioè è $f$ è periodica
- $f(0,\varphi)=f_{0},\; \forall \varphi$ e $f(\pi,\varphi)=f_{\pi},\; \forall \varphi$. Il valore nei poli è uguale arrivando da qualunque direzione.

Sulla base di queste considerazioni è anche vero che:
$$
	L_{-}=L^{\dagger}_{+}
$$
A questo punto ci manca $L^2$. Calcolandolo otteniamo:
$$
	L^2=-\hbar^2\left[ \frac{ \partial^2  }{ \partial \theta^2 } +\frac{\cos \theta}{\sin \theta} \frac{ \partial  }{ \partial \theta } +\frac{1}{\sin^2\theta} \frac{ \partial^2  }{ \partial \varphi^2 }  \right]
$$
Tutti gli operatori che si servono sono dunque:
$$
	\begin{cases}
		L^2=-\hbar^2\left[ \frac{ \partial^2  }{ \partial \theta^2 } +\frac{\cos \theta}{\sin \theta} \frac{ \partial  }{ \partial \theta } +\frac{1}{\sin^2\theta} \frac{ \partial^2  }{ \partial \varphi^2 }  \right] \\
		L_{\pm}=\pm \hbar e^{ \pm i\varphi }\left[ \frac{ \partial  }{ \partial \theta } \pm i \frac{\cos \theta}{\sin \theta}\frac{ \partial  }{ \partial \varphi }  \right] \\
		L_{z}=-i\hbar \frac{ \partial  }{ \partial \varphi } 
	\end{cases}
$$
Cerchiamo le autofunzioni di questi operatori.
Per farlo, anzichè risolvere l'eq. diff., risolviamo il problema agli autovalori.

**Caso $L_{z}$**.
$$
	\begin{aligned}
	L_{z}f_{m}(\varphi)&=\hbar m f_{m}(\varphi) \\
	&=-i\hbar \frac{df_{m}}{d\varphi}=\hbar mf_{m}(\varphi)\\
	\implies & f_{m}(\varphi)=Ne^{ im\varphi }
	\end{aligned}
$$
Andando a normalizzare sull'intervallo $[0,2\pi)$ troviamo:
$$
	f_{m}(\varphi)=\frac{1}{\sqrt{ 2\pi }}e^{ im\varphi }
$$
Imponiamo la periodicità:
$$
	\frac{1}{\sqrt{ 2\pi }}e^{ im\varphi }=f_{m}(\varphi)=f_{m}(\varphi+2\pi)=\frac{1}{\sqrt{ 2\pi }}e^{ im(\varphi+2\pi) }
$$
Ma abbiamo detto di voler soltanto funzioni monodrome, dunque $m\in \mathbb{Z}$.
I valori seminteri di $m$ non sono ammessi quando realizziamo l'algebra del momento angolare in termini di operatori differenziali su $S^2$.

**Achtung!** Se scegliesi un valore semintero di $m$ il mio risultato varierebbe solo per una differenza di segno (cioè una differenza di fase), e abbiamo più volte detto che a meno di una differenza di fase due vattori $\ket{\alpha}$ e $e^{ i\theta }\ket{\alpha}$ rappresentano lo stesso stato! Allora dov'è il problema? In realtà il problema è molto più delicato ma il risultato finale è l'esclusione dei seminteri.

Ma l'algebra di $SO(3)$ (o $SU(2)$), cioè l'algebra del momento angolare, può essere realizzata con $j,m$ semi-interi in termini di MATRICI FINITE.
Ad esempio:

**Matrici di Pauli**
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

**OSS:** le matrici di Pauli 2-d, a differenza di quelle 3-d, sono matrici complesse, pertanto acquisiscono senso soltanto nell'ambito della meccanica quantistica.

### Armoniche sferiche

Definiamo:
$$
	Y^m_{l}(\theta,\varphi)\equiv \braket{ \theta,\varphi | l,m } 
$$
$$
	L_{\pm}\ket{l,m} =\sqrt{ l(l+1)-m(m\pm 1) } \ket{l,m\pm1} 
$$
Scegliamo di usare $L_{-}$ e usiamo il fatto che:
$$
	L_{-}\ket{l-l} =0
$$
Uso la completezza su $\{ \ket{\theta,\varphi} \}$.
$$
	\int^1_{-1} d\cos \theta \int^{2\pi}_{0} \ket{\theta,\varphi} \bra{\theta,\varphi} =\mathbb{1}
$$
Dunque.
$$
	\int^1_{-1}d\cos \theta \int^{2\pi}_{0} d\varphi\,\underbrace{\bra{\theta',\varphi'} L_{-}\ket{\theta,\varphi} }_{\delta(\cos \theta-\cos \theta')\delta(\varphi-\varphi')L_{-}^{\text{op. diff.}}}\underbrace{\braket{ \theta,\varphi | l,-l }}_{Y^{-l}_{l}(\theta,\varphi)} =0
$$
$$
	\implies \left( \frac{ \partial  }{ \partial \theta } -i \frac{\cos \theta}{\sin \theta} \frac{ \partial  }{ \partial \varphi }  \right)Y^{-l}_{l}(\theta,\varphi)=0
$$
Supponiamo in maniera un po' arbitraria che la soluzione sia fattorizzabile e procediamo per separazione di variabili.
$$
	Y^{-l}_{l}(\theta,\varphi)=A(\theta)B(\varphi)
$$
Sostituendo nell'eq. diff. otteniamo:
$$
	B(\varphi) \frac{dA}{d\theta}-i \frac{\cos \theta}{\sin \theta}A(\theta) \frac{dB}{d\varphi}=0
$$
porto tutta la dipendenza di $\varphi$ da un lato e quella da $\theta$ dall'altro.
$$
	\frac{1}{A(\theta)} \tan \theta \, \frac{dA}{d\theta}=\frac{1}{B(\varphi)} \frac{dB}{d\varphi}=K
$$
Entrambe devono valere separatamente, dunque:
$$
	B(\varphi)=Ne^{ -iK\varphi } \implies k=l
$$
è la stesso che ho trovato prima!
L'altra equazione è:
$$
	\tan\theta \frac{ dA}{d\theta}=lA(\theta)
$$
per risolverla cambiamo variabile. Sia $z=\sin \theta \implies dz=\cos \theta d\theta$, $A(\theta)\to \tilde{A}(\theta)$.
$$
	z\frac{d\tilde{A}}{dz}=l \tilde{A}(z) \implies \frac{d\tilde{A}}{\tilde{A}}=l \frac{dz}{z}
$$
Dunque:
$$
	\tilde{A}(z) \sim z^l \implies A(\sin \theta) \sim(\sin \theta)^l
$$
Pertanto:
$$
	Y_{l}^{-l}(\theta,\varphi) =N (\sin \theta)^l e^{ -il\varphi }
$$
Normalizziamola:
$$
	\begin{aligned}
	1&=\underbrace{(Y^{-l}_{l}, Y^{-l}_{l})}_{\iff \braket{ l,-l | l,-l } =1}= |N|^2 \int^1_{-1}d\cos \theta \int^{2\pi}_{0} d\varphi\, (\sin \theta)^2l=\\
	&=|N|^2 2\pi \int^1_{-1} dx\, (1-x^2)^{l}
	\end{aligned}
$$
con un cambio di variabili intelligente: $t=\frac{1+x}{2}\implies x=2t-1$,
$\begin{cases}(1-x)=2(1-t) \\  (1+x)=2t\end{cases}\quad dx=2tdt$
Arriviamo a:
$$
	1=2\pi |N|^2 2^{2l+1} \underbrace{\int^1_{0} dt\, t^l (1-t)^l}_{B(l+1,l+1)}=2\pi |N|^2 2^{2l} \frac{(l!)^2}{(2l+1)!}
$$
E troviamo:
$$
	Y^{-l}_{l}(\theta,\varphi)= \frac{1}{2^l l!} \sqrt{ \frac{(2l+1)!}{4\pi} } (\sin \theta)^l e^{ -il }
$$
Le armoniche successive si costruiscono mediante l'operatore gradino.
$$
	\frac{1}{\hbar} L_{+}^{\text{op. diff}} Y_{l}^m(\theta,\varphi)=\sqrt{ l(l+1)-m(m+1) }Y_{l}^{m+1}(\theta,\varphi)
$$

