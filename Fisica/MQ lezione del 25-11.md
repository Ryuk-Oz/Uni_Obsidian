
Scriviamo l'operatore di rotazione di un angolo $\delta \varphi$, cioè l'operatore che ci da una trasformazione infinitesima.
$$
	\mathcal{R}_{z}(\delta \varphi)= \mathbb{1}-\delta \varphi \frac{ \partial  }{ \partial \varphi } +O(\delta \varphi^2)\to e^{ -\delta \varphi \frac{ \partial  }{ \partial \delta \varphi }  }
$$
Cosa succede con campi vettoriali?
Studiamo un esempio:
$$
	\begin{cases}
	A_{x}(x,y,z)=y \\
	A_{y}(x,y,z)=0 \\
	A_{z}(x,y,z)=0
	\end{cases}
$$
![[Pasted image 20261125090201.png|320]]

Cosa succede se provo ad applicargli una rotazione?
$$
	\begin{cases}
	x=x' \cos \varphi-y'\sin \varphi \\
	y=-x'\sin \varphi+y'\cos \varphi \\
	z=z'
	\end{cases}
$$
Il campo vettoriale diventa:
$$
\begin{cases}
A_{x}=x'\sin \varphi+y'\cos \varphi \\
A_{y}=0 \\
A_{z}=0
\end{cases}
$$
Analogamente a quanto fatto prima, devo identificare il nuovo vettore con il vecchio.
Per un vettore, una rotazione non modifica solo le coordinate ma mescola anche le componenti.
In particolare troviamo:
$$
	\begin{cases}
	A'_{x}=A_{x}\cos \varphi+A_{y}\sin \varphi=x'\sin \varphi \cos \varphi+y'^2\cos^2 \varphi \\
	A'_{y}=-A_{x}\sin \varphi+A_{y}\cos \varphi=-x'\sin^2\varphi+y'\sin \varphi \cos \\var\phi
	A'_{z}=A_{z}=0
	\end{cases}
$$
verifichiamo che questo abbia senso.
Prendiamo ad esempio una rotazione di $\frac{\pi}{2}$ e $\pi$.
![[Pasted image 20261125090953.png]]
La "freccia fisica" resta invariata.
$$
	\begin{cases}
	\varphi'(\vec{x}')=\varphi(\vec{x}) \\
	\vec{A}'(\vec{x}')=\vec{A}(\vec{x})
	\end{cases}
$$
Cerchiamo la trasformazione infinitesima
$$
	\vec{A}'(\vec{x})=\begin{pmatrix}
	x\sin \varphi \cos \varphi+y\cos^2\varphi \\
	-x\sin^2\varphi+y\sin \varphi \cos \varphi \\
	0 
	\end{pmatrix}\underset{\varphi\to{0}}{\to} \begin{pmatrix}
	\varphi x+y \\
	-\varphi y \\
	0
	\end{pmatrix}
$$
Dunque:
$$
	\delta \vec{A}(\vec{x})\equiv\vec{A}'(\vec{x})-\vec{A}(\vec{x})=\varphi \begin{pmatrix}
	x \\
	-y \\
	0
	\end{pmatrix}=\delta_{1} \vec{A}+\delta_{2} \vec{A}
$$
con:
$$
	\delta_{1}\vec{A}=\varphi(x\partial_{y}-y \partial_{x})\vec{A}=\varphi(x \partial_{y}-y\partial_{x})\begin{pmatrix}
	y \\
	0 \\
	0
	\end{pmatrix}=\varphi \begin{pmatrix}
	x \\
	0 \\
	0
	\end{pmatrix}
$$
$$
	\delta_{2}\vec{A}=\varphi r_{z}\vec{A}=\varphi \begin{pmatrix}
	0 & 1 & 0 \\
	-1 & 0 & 0 \\
	0 & 0 & 0
	\end{pmatrix}\begin{pmatrix}
	y \\
	0 \\
	0
	\end{pmatrix}=\varphi \begin{pmatrix}
	0 \\
	-y \\
	0
	\end{pmatrix}
$$
Possiamo quindi riscrivere ulteriormente:
$$
	\delta \vec{A}(\vec{x})=\varphi\left( \frac{ \partial  }{ \partial \varphi } +r_{z} \right)\vec{A}(\vec{x})
$$
L'operatore è dunque:
$$
	\mathcal{R_{z}}=\exp\left[ \delta \varphi \frac{ \partial  }{ \partial \varphi }  \right](\exp[\delta \varphi\, r_{z}])
$$
$\frac{ \partial  }{ \partial \varphi }$ è il momento angolare, invece $r_{z}$ è ciò che chiameremo Spin.
Osservazione, questo esiste anche in Meccanica Classica!
Servono a rappresentare oggetti con trasformazioni non banali sotto gruppo delle rotazioni. Ciò che è esclusivo della meccanica quantistica è la possibilità di avere valori di $j$ seminiteri.

Passiamo alla meccanica quantistica.
In MQ le funzioni d'onda che abbiamo incontrato fin'ora si comportano come campi scalari

1. Traslazioni ($d=1$):
$$
	\varphi'(x)=T(a)\psi(x)=e^{ -a \frac{d}{dx} }\psi(x)=e^{ -\frac{i}{\hbar}a\hat{p}_{x} }\psi(x)
$$
   E l'operatore impulso è il generatore infinitesimo delle traslazioni.
   Generalizzando a $d=3$ abbiamo invece:
$$
	\psi'(\vec{r})=T(\vec{a})\psi(\vec{r})=e^{ -\frac{i}{\hbar}\vec{a}\cdot \vec{p} }\psi(\vec{r})\quad \text{ con } \quad \vec{p}=-i\hbar \vec{\nabla}
$$
2. Rotazioni (attorno all'asse $z$):
$$
   	\psi'(r,\theta,\varphi)=\mathcal{R}_{z}(\delta \varphi)\psi(r,\theta,\varphi)=e^{ -\delta \varphi \frac{ \partial  }{ \partial \varphi }  }\psi(r,\theta,\varphi)=\exp\left[ -\frac{i}{\hbar}\delta \varphi\, L_{z} \right]\psi(r,\theta,\varphi)
   $$
   Cioè il momento angolare è il generatore infinitesimo delle rotazioni
   Posso riscriverlo anche come:
$$
	\psi'(r,\theta,\varphi)=\exp\left[ -\frac{i}{\hbar} \delta \varphi\, \hat{n}_{z}\cdot \vec{L} \right]\psi
   $$
   In generale per una rotazione di un angolo $\delta \varphi$ attorno ad un asse generico caratterizzato da un versore $\vec{n}$:
   $$
	\psi'(r,\theta,\varphi)=e^{ -\frac{i}{\hbar} \delta \varphi \,\hat{n}\cdot \vec{L} }\psi(r,\theta,\varphi)
   $$
In meccanica quantistica possono esistere dei campi vettoriali? Delle funzioni d'onda multicomponenti $\vec{\psi}$? La risposta a questa domanda è empirica ed è affermativa.

Se esistono $\psi$ a molte componenti $\psi_{\alpha}$:
$$
\psi'_{\alpha}(r,\theta,\varphi)=\exp\left[ -\frac{i}{\hbar}\delta \varphi\, \vec{n}\cdot \vec{L} \right]\left( \exp\left[ -\frac{i}{\hbar}\delta \varphi\,\vec{n}\cdot \vec{S} \right] \right)_{\alpha \beta}\psi_{\beta}(r,\theta,\varphi)
$$
Dall'algebra del momento angolare:
$$
	[L_{i},L_{j}]=i\hbar \varepsilon_{ijk}L_{k}
$$
deduciamo che:
$$
	[S_{i},S_{j}]=i\hbar\varepsilon_{ijk}S_{k}
$$
Con $S_{i}$ matrici (a differenza di $L_{i}$ che sono operatori differenziali).
Queste matrici esistono per ogni $d$ e sono le matrici $(2j+1)\times(2j+1)$ che abbiamo già trovato per $j=0, \frac{1}{2}, 1, \frac{3}{2}, ecc\dots$.
$j$ è ciò che chiamiamo spin.

### Spin semi-intero

Il caso (ad esempio) di SPIN $\frac{1}{2}$ ($j= \frac{1}{2}$, $2j+1=2$) non ha equivalente classico perchè necessita del piano complesso.
$$
	\sigma_{x}=\begin{pmatrix}
	0 & 1 \\
	-1 & 0
	\end{pmatrix} \quad \sigma_{y}=\begin{pmatrix}
	0 & -i \\
	i & 0
	\end{pmatrix} \quad \sigma_{z}=\begin{pmatrix}
	1 & 0 \\
	0 & -1
	\end{pmatrix}
$$
E otteniamo:
$$
	S_{i}\equiv \frac{\hbar}{2} \sigma_{i} \implies[S_{i},S_{j}]=i\hbar \varepsilon_{ijk} S_{k}
$$
$$
	S^2 \equiv S_{x}^2+S_{y}^2+S_{z}^2= \frac{3}{4} \hbar^2 \mathbb{1}
$$

Quali sono i problemi in meccanica classica?
- Sono matrici complesse, dunque quete rappresentazioni di $\vec{J}$ non sono utilizzabili in MC
- Una rotazione di $2\pi$ attorno a un asse produce un cambio di segno
$$
	\begin{aligned}
	R^{1/2}_{z}(2\pi):\quad \begin{pmatrix}
	\psi_{1} \\
	\psi_{2}
	\end{pmatrix}\to \begin{pmatrix}
	\psi_{1}' \\
	\psi_{2}'
	\end{pmatrix}&=\underbrace{R_{z}^{1/2}}_{e^{ -i/\hbar \, 2\pi S_{z}}} (2\pi)\begin{pmatrix}
	\psi_{1} \\
	\psi_{2}
	\end{pmatrix}= \\
	&=e^{ -i\pi \sigma_{z} }\left[ \psi_{1}\begin{pmatrix}
	1 \\
	0
	\end{pmatrix}+\psi_{2}\begin{pmatrix}
	0 \\
	1
	\end{pmatrix} \right] = \\
	&= e^{ -i\pi }\psi_{1}\begin{pmatrix}
	1 \\
	0
	\end{pmatrix}+e^{ i\pi }\psi_{2} \begin{pmatrix}
	0 \\
	1
	\end{pmatrix}=-\begin{pmatrix}
	\psi_{1} \\
	\psi_{2}
	\end{pmatrix}
	\end{aligned}
  $$
  Questa funzione d'onda rappresenta lo stesso STATO FISICO di $\begin{pmatrix}\psi_{1} \\  \psi_{2}\end{pmatrix}$
Perchè in questo caso ci accolliamo l'ambiguità di segno ma per $m$ no?
Posso accettare un armonica sferica della forma $Y_{\frac{1}{2}}^m$?
Consideriamo ad esempio:
$$
	Y_{\frac{1}{2}}^{\frac{1}{2}}\sim e^{ i\varphi/ 2}
$$
Cosa succede quando entra in gioco anche $\theta$?
$$
	Y_{l}^{-l} \sim (\sin \theta)^l e^{ -il\varphi }
$$
E ho che:
$$
	Y^{-\frac{1}{2}}_{\frac{1}{2}} \sim \sqrt{ \sin \theta }e^{ -i\varphi/2 }
$$
E so che $L_{+}Y^{-\frac{1}{2}}_{\frac{1}{2}}\to Y^{\frac{1}{2}}_{{\frac{1}{2}}}$.
Ricostruindo $Y^{\frac{1}{2}}_{\frac{1}{2}}$ in questo modo otteniamo un risultato diverso da quello che otteniamo costruendo l'armonica da 0. Non è possibile costruire uno spettro coerente.




   
