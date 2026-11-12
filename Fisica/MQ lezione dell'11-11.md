
Continuiamo a trattare le armoniche sferiche

$$
	Y^{-l}_{l}(\theta,\varphi)= \frac{1}{2^l l!} \sqrt{ \frac{(2l+1)!}{4\pi} } (\sin \theta)^l e^{ -il }
$$
per trovare le altre uso la seguente equazione:
$$
	\frac{1}{\hbar} L_{+}^{\text{op. diff}} Y_{l}^m(\theta,\varphi)=\sqrt{ l(l+1)-m(m+1) }Y_{l}^{m+1}(\theta,\varphi)
$$
Con:
$$
	L_{+}=\hbar e^{ i\phi } \left( \frac{ \partial  }{ \partial \theta } + \frac{\cos \theta}{\sin \theta} \frac{ \partial  }{ \partial \varphi }  \right)
$$
Procediamo in maniera analoga a quanto fatto per l'oscillatore armonico.
Queste funzioni sono ortogonali su $L^2(\theta \in [0,\pi],\varphi\in[0,2\pi)$, allora ci aspettiamo che emerga un'ulteriore famiglia di polinomi ortogonali.

Per le a.s. vale l'ortonormalità.
$$
	(Y_{l}^m, Y_{l'}^{m'})= \int^1_{-1} d\cos \theta \int^{2\pi}_{0} d\varphi (Y^m_{l}(\theta,\varphi))^*Y_{l'}^{m'}(\theta,\varphi) = \delta_{l,l'} \delta_{m,m'}
$$
E la completezza:
$$
	\sum^\infty_{l=0} \sum^l_{m=-l} Y^m_{l}(\theta,\varphi)(Y^m_{l}(\theta',\varphi'))^*=\delta(\cos \theta-\cos \theta')\delta(\varphi-\varphi')
$$
Se valgono queste due cose, le armoniche sferiche formano una base ortonormale di $L^2(S^2)$ e:
$\forall f(\theta,\varphi)\in L^2(S^2)$: $f(\theta,\varphi)=\sum^\infty_{l=0}\sum^l_{m=-l}C^{(f)}_{lm}Y^l_{m}(\theta,\varphi)$
con:
$$
	C^{(f)}_{lm}=(Y_{l}^m,f)=\int^1_{-1}d\cos \theta \int^{2\pi}_{0} d\varphi\, (Y_{l}^m(\theta,\varphi))^* f(\theta,\varphi)
$$
Se volessimo calcolare in maniera esplicita le armoniche sferiche, dovremmo fare uso dei Polinomi di Legendre.

Anche per i polinomi di Legendre esiste una formula di Rodrigues:ù
$$
	P_{l}(x)=\frac{1}{2^l l!}\left( \frac{d}{dx} \right)^l (x^2-1)^l
$$
si tratta di polinomi di grado $l$.
All'interno delle armoniche sferiche, queste compaiono con argomento $\cos \theta$.
Calcoliamo i primi polinomi:
$$
	\begin{cases}
	P_{0}(x)=1 \\
	P_{1}(x)=x \\
	P_{2}(x)=\frac{1}{2}(3x^2-1)
	\end{cases}
$$
Da questi polinomi è possibile costruire le funzioni associate di Legendre:
$$
	\begin{cases}
	P_{l}^m(x) \equiv(-1)^m (1-x^2)^{m/2} \left( \frac{d}{dx} \right)^m P_{l}(x), &  m\geq 0 \\
	P_{l}^{-m}(x)=(-1)^{m} \frac{(l-m)!}{(l+m)!}P_{l}^m(x)
	\end{cases}
$$
e:
$$
	P_{l}^m(x)=P_{l}^{-m}=0, \quad \text{se } |m|>l
$$
A questo punto possiamo scrivere in maniera esplicita le armoniche sferiche.
$$
	Y_{l}^m(\theta,\varphi) = \sqrt{ \frac{2l+1}{4\pi} \frac{(l-m)!}{(l+m)!} } e^{ im\varphi }P_{l}^m(\cos \theta)
$$
Le armoniche sferiche sono piene di proprietà, in particolare ci tornerà utile la seguente proprietà:
$$
	Y_{l}^{-m}(\theta,\varphi) = (-1)^m (Y_{l}^m(\theta,\varphi))^*
$$
Per familiarizzare con le armoniche sferiche, scriviamone un paio.
$$
	\begin{aligned}
	Y^0_{0}(\theta,\varphi)&= \frac{1}{\sqrt{ 4\pi }}\\
	Y^{-1}_{1}(\theta,\varphi) &= \sqrt{ \frac{3}{8\pi} }\sin \theta  \; e^{ -i\varphi }; \quad Y_{1}^0=\sqrt{ \frac{3}{4\pi} }\cos \theta; \quad Y^1_{1}=-\sqrt{ \frac{3}{8\pi} }\sin \theta\,e^{ i\varphi }\\
	Y^0_{2}(\theta,\varphi)&= \sqrt{ \frac{5}{4\pi} }(3\cos^2\theta-1); \quad Y_{2}^{\pm1} =\mp \sqrt{ \frac{15}{8\pi} }\sin \theta \cos \theta\, e^{ \pm i\varphi }; \quad \text{ecc...}
	\end{aligned}
$$

### Verso l'atomo di Idrogeno

#### Excursus sul problema dei 2 corpi

Consideriamo 2 particelle di masse $m_{1}$ e $m_{2}$ interagenti con un potenziale $V(\vec{r}_{1}-\vec{r}_{2})$, $\vec{r}_{1}-\vec{r}_{2}$ rappresenta l'invarianza per traslazione.
Classicamente abbiamo un'Hamiltoniana:
$$
	H=\frac{|\vec{p}_{1}|^2}{2m_{1}}+\frac{|\vec{p}_{2}|^2}{2m_{2}}+V(\vec{r}_{1}-\vec{r}_{2})
$$
Quantisticamente $H\to \hat{H}$, cerco $\psi(\vec{r}_{1},\vec{r}_{2})$.
Scelgo come nuove coordinate:
$$
	\begin{cases}
	\vec{r}\equiv \vec{r}_{1}-\vec{r}_{2} & \text{posizione relativa} \\
	\vec{R}= \frac{m_{1}\vec{r}_{1}+m_{2}\vec{r}_{2}}{m_{1}+m_{2}} & \text{posizione del centro di massa}
	\end{cases}
$$
riscrivo temporaneamente $\hat{H}$ con le vecchie coordinate.
$$
	\left[ -\frac{\hbar^2}{2m_{1}} \Delta_{1}-\frac{\hbar^2}{2m_{2}} \Delta_{2}+V(\vec{r}_{1}-\vec{r}_{2}) \right]\psi(\vec{r}_{1},\vec{r}_{2})=E_{tot}\psi(\vec{r}_{1},\vec{r}_{2})
$$
Cambiamo coordinate.
$$
	\frac{ \partial  }{ \partial x_{1} }=\frac{ \partial x }{ \partial x_{1} } \frac{ \partial  }{ \partial x } +\frac{ \partial X }{ \partial x_{1} } \frac{ \partial  }{ \partial X } =\frac{ \partial  }{ \partial x } +\frac{m_{1}}{m_{1}+m_{2}}\frac{ \partial  }{ \partial X } 
$$
e:
$$
	\frac{ \partial  }{ \partial x_{2} } =-\frac{ \partial  }{ \partial x } + \frac{m_{2}}{m_{1}+m_{2}}\frac{ \partial  }{ \partial X } 
$$
...MA... nel laplaciano sono presenti le derivate seconde:
$$
\begin{aligned}
	\frac{ \partial ^2 }{ \partial x_{1}^2 } &=\left( \frac{ \partial  }{ \partial x } +\frac{m_{1}}{m_{1}+m_{2}} \frac{ \partial  }{ \partial X }  \right)^2\\
	&=\frac{ \partial^2  }{ \partial x^2 } +\frac{2m_{1}}{m_{1}+m_{2}}\frac{ \partial  }{ \partial x } \frac{ \partial  }{ \partial X } +\left( \frac{m_{1}}{m_{1}+m_{2}} \right)^2 \frac{ \partial^2  }{ \partial X^2 } 
\end{aligned}
$$
e:
$$
	\frac{ \partial^2  }{ \partial x_{2}^2 }= \frac{ \partial^2  }{ \partial x^2 } -\frac{2m_{2}}{m_{1}+m_{2}}\frac{ \partial  }{ \partial x } \frac{ \partial  }{ \partial X } +\left( \frac{m_{2}}{m_{1}+m_{2}} \right)^2 \frac{ \partial^2  }{ \partial X^2 } 
$$
dunque:
$$
	\begin{aligned}
	&-\frac{\hbar^2}{2m_{1}}\Delta_{1}-\frac{\hbar^2}{2m_{2}}\Delta_{2} =\\
	=& -\frac{\hbar^2}{2m_{1}}\left( \Delta_{r}+\frac{m_{1}^2}{(m_{1}+m_{2})^2}\Delta _{R}+ \cancel{\frac{2m_{1}}{m_{1}+m_{2}} \vec{\nabla }_{r} \cdot \vec{\nabla}_{R}} \right)-\\
	&-\frac{\hbar^2}{2m_{2}}\left( \Delta_{r}+\frac{m_{2}^2}{(m_{1}+m_{2})^2}\Delta _{R}+ \cancel{\frac{2m_{2}}{m_{1}+m_{2}} \vec{\nabla }_{r} \cdot \vec{\nabla}_{R}} \right)\\
	=&-\frac{\hbar^2}{2} \left( \frac{1}{m_{1}}+\frac{1}{m_{2}} \right)\Delta_{r}-\frac{\hbar^2}{2(m_{2}+m_{1})}\Delta_{R}=-\frac{\hbar^2}{2\mu}\Delta_{r}-\frac{\hbar^2}{2M}\Delta_{R}
	\end{aligned}
$$
con $\mu= \frac{m_{1}m_{2}}{m_{1}+m_{2}}$, massa ridotta e $M=m_{1}+m_{2}$ massa totale.
Abbiamo riscitto l'edS in una forma semplice che è direttamente separabile.
$$
	\left[ -\frac{\hbar^2}{2\mu}\Delta_{r}-\frac{\hbar^2}{2M}\Delta_{R}+V(\vec{r}) \right]\psi(\vec{r},\vec{R})=E_{tot}\psi(\vec{r},\vec{R})
$$
Supponiamo che $\psi(\vec{r},\vec{R})$ sia fattorizzabile:
$$
	\psi(\vec{r},\vec{R})=\psi_{1}(\vec{r})\psi_{2}(\vec{R})
$$
a questo punto possiamo ottenere le 2 equazioni:
$$
	\begin{aligned}
	&\left( -\frac{\hbar^2}{2\mu}\Delta_{r}+V(\vec{r}) \right)\psi_{1}(\vec{r})=E_{1}\psi_{1}(\vec{r})\\
	&\left( -\frac{\hbar^2}{2M} \Delta_{R} \right)\psi_{2}(\vec{R})=E_{2}\psi_{2}(\vec{R})
	\end{aligned}
$$
con $E_{tot}=E_{1}+E_{2}$.
(RIVEDI APPUNTI MAGNEA PER INTERPRETAZIONE FISICA).

#### Stati stazionari in potenziali centrali $V=V(r)$

Nel caso di potenziali centrali sappiamo che le coordinate sferiche sono la scelta più comoda, ma abbiamo un problema, la presenza del laplaciano nell'eds. 
Riscriviamo quindi il laplaciano in coordinate sferiche.
Lo studio del laplaciano equivale allo studio di $|\vec{p}|^2$.
$$
	|\vec{p}|^2=\left| \frac{\vec{r}\cdot \vec{p}}{\vec{r}}\right|^2+\left| \frac{\vec{r}\wedge \vec{p}}{r}\right|^2=p_{r}^2+\frac{|\vec{L}|^2}{r^2}
$$
Problema:
$$
	p_{r}\equiv \frac{\vec{r}\cdot \vec{p}}{r}
$$
non è Hermitiano nè, tantomeno, autoaggiunto!
$$
	\frac{\vec{r}\cdot \vec{p}}{r}=-i\hbar \frac{\vec{r}\cdot \vec{\nabla}}{r}=-i\hbar\left( \frac{x}{r}\frac{ \partial  }{ \partial x } +\frac{y}{r}\frac{ \partial  }{ \partial y } +\frac{z}{r}\frac{ \partial  }{ \partial z }  \right)=-i\hbar \frac{ \partial  }{ \partial r } 
$$
$\frac{ \partial  }{ \partial r }$ non è Hermitiano, VERIFICA.

Definisco un operatore autoaggiunto. Come?
Sfrutto il fatto che $(xp_{x})^{\dagger}=p_{x}x$.
$$
	p_{r}\equiv \frac{1}{2}\left( \frac{\vec{r}}{r}\cdot \vec{p}+\vec{p}\cdot \frac{\vec{r}}{r} \right)=-\frac{i\hbar}{2}\left( \frac{\vec{r}}{r}\cdot \vec{\nabla}+\vec{\nabla}\cdot \frac{\vec{r}}{r} \right)
$$
Voglio riscriverlo in maniera più furba, tale che agisca sempre a destra.
$$
\begin{aligned}

	\vec{\nabla}\cdot\left( \frac{\vec{r}}{r}f \right)&=\frac{\vec{r}}{r}\cdot \vec{\nabla f}+\frac{f}{r} \vec{\nabla}\cdot \vec{r}+\vec{r}f\nabla\left( \frac{1}{r} \right)=\\
	&=\frac{\vec{r}}{r} \cdot \vec{\nabla}f+\frac{3}{r}f-\frac{1}{r}f=\frac{\vec{r}}{r}\cdot \vec{\nabla}f+\frac{2}{r}f
\end{aligned}
$$
e ottengo:
$$
	p_{r}=-i\hbar \left( \frac{ \partial  }{ \partial r } +\frac{1}{r} \right)
$$
$$
	p_{r}^2=-\hbar^2\left( \frac{ \partial  }{ \partial r } +\frac{1}{r} \right)^2=-\hbar^2 \frac{1}{r^2}\frac{ \partial  }{ \partial r } \left( r^2 \frac{ \partial  }{ \partial r }  \right)=-\hbar^2 \left( \frac{ \partial^2  }{ \partial r^2 } +\frac{2}{r}\frac{ \partial  }{ \partial r }  \right)
$$
A questo punto è lecito chiedersi, $p_{r}^2$ è autoaggiunto o solo Hermitiano? Devo fare delle restrizioni sul dominio?

Immagino di avere $\psi(r)\sim \frac{1}{r}$ per $r\to{0}$, $\overset{?}{\in}L^2(\mathbb{R}^3)$
$$
	\int_{0}^\infty dr \, r^2 |\psi(r)|^2
$$
è sempre integrabile in $0$, già $\psi(r)\sim \frac{1}{r^2}$ non lo è.
Se vi applico $p^2_{r}$ invece? Se $\psi(r)\sim \frac{1}{r}$, allora $p^2_{r}\psi(r)\sim \frac{1}{r^3} \not\in L^2 (\mathbb{R}^3)$.
Dunque $\psi(r)$ non è nel dominio di $p^2_{r}$.

ricordando che $|\vec{p}|^2\to-\hbar^2 \Delta$:
$$
	\Delta = \frac{1}{r^2} \frac{ \partial  }{ \partial r } r^2 \frac{ \partial  }{ \partial r } -\frac{|\vec{L}|^2}{\hbar^2 r^2}
$$
Ora possiamo sostituire tutto nell'edS e risolvere per separazione di variabili.
$$
	\left( \frac{p_{r}^2}{2\mu}+\frac{|\vec{L}|^2}{2\mu r^2}+V(r)-E\right)\psi(\vec{r})=0
$$
fattorizzo la soluzione:
$$
	\psi(\vec{r})=\psi(r)Y(\theta,\varphi)
$$
e ottengo:
$$
	Y(\theta,\varphi)\left[ \frac{p^2_{r}}{2\mu}+V(r)-E \right]\varphi(r)+\frac{\varphi(r)}{2\mu r^2}|\vec{L}|^2 Y(\theta,\varphi)=0
$$
$$
	\frac{1}{\varphi(r)}\left[ \left( \frac{p_{r}^2}{2\mu} \varphi(r) \right)+V(r)-E \right]2\mu r^2=-\frac{1}{Y(\theta,\varphi)}|\vec{L}|^2Y(\theta,\varphi)=-\lambda
$$
e ottengo 2 equazioni:
$$
	|\vec{L}|^2Y(\theta,\varphi)=\lambda Y(\theta,\varphi)
$$
$$
	\left( \frac{p_{r}^2}{2\mu}+V(r)-E \right)\varphi(r)=-\frac{\lambda}{2\mu r^2}\varphi(r)
$$
La prima equazione ci dice che $Y(\theta,\varphi)$ è una qualsiasi armonica sferica, $Y^m_{l}(\theta,\varphi)$ e $\lambda=\hbar^2 l(l+1)$. 
Sostituiamo $\lambda$ nella seconda equazione:
$$
	-\frac{\hbar^2}{2\mu}\left( \frac{d^2}{dr^2}+\frac{2}{r} \frac{d}{dr} \right)\varphi(r)+\left( V(r)+ \frac{\hbar l(l+1)}{2\mu r^2} \right)\varphi(r)=E\varphi(r)
$$
Equazione Radiale di Shrödinger.






