
Definiamo:
$$
	Y^m_{l}(\theta,\varphi)\equiv \braket{ \theta,\varphi | l,m } 
$$
$$
	L_{\pm}\ket{l,m} =\sqrt{ l(l+1)-m(m\pm 1) } \ket{l,m\pm1} 
$$
Scegliamo di usare $L_{-}$ e sfruttiamo il fatto che:
$$
	L_{-}\ket{l,-l} =0
$$
Ricordiamo:
$$
	L_{+}=\hbar e^{ i\phi } \left( \frac{ \partial  }{ \partial \theta } + \frac{\cos \theta}{\sin \theta} \frac{ \partial  }{ \partial \varphi }  \right)
$$
Uso la completezza su $\{ \ket{\theta,\varphi} \}$.
$$
	\int^1_{-1} d\cos \theta \int^{2\pi}_{0} \ket{\theta,\varphi} \bra{\theta,\varphi} =\mathbb{1}
$$
Dunque:
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
	\frac{1}{A(\theta)} \tan \theta \, \frac{dA}{d\theta}=\frac{i}{B(\varphi)} \frac{dB}{d\varphi}=K
$$
Entrambe devono valere separatamente, dunque:
$$
	B(\varphi)=Ne^{ -iK\varphi } \implies k=l
$$
è la stesso che ho trovato prima!
(Prima ho trovato $e^{ im\varphi }$, ma in questo caso $m=-l$).
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

**Argomento Associato:** [[Autofunzioni del momento angolare, armoniche sferiche]]