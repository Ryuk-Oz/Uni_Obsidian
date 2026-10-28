
**Utile da rivedere:** [[Probabilità condizionata e formula di Bayes]], [[2.Probabilità condizionata]]

Occupiamoc dello studio della probabilità condizionata nel caso continuo. Nel caso continuo la probabilità di un evento $X$ crolla a 0 e ha misura nulla rispetto allo spazio degli eventi, questo causa dei problemi, che adesso analizzeremo in un caso semplice.
Consideriamo una sfera di raggio $R$ e studiamo la probabilità di trovarci in un punto preciso su di un cerchio massimo, sapendo di trovarci già su un cerchio massimo. Quello che troviamo è che cambiando il cerchio massimo considerato cambia anche la probabilità condizionata che stiamo cercando di calcolare. Inutile dire che questo è un bel problema.
Studiamo un modello bidimensionale semplificato per capire quale sia l'origine del problema.
Considero la semicirconferenza di raggio unitario in figura.

![[Pasted image 20261008085649.png|548]]

Ipotizziamo una distribuzione di probabilità uniforme all'interno della circonferenza:
$$
	p_{X,Y}(x,y)=\frac{2}{\pi}; \quad \int_{S}dxdy\,p_{X,Y}(x,y)=1
$$
Qual è la probabilità di trovarsi sulla metà superiore del raggio?
Intuitivamente, poichè la distribuzione è uniforme, ci verrebbe da pensare:
$$
	P\left( Y\geq \frac{1}{2}|X=0 \right)=\frac{1}{2}
$$
Ma il raggio ha misura nulla rispetto al semicerchio quindi questa probabilità è più complessa da calcolare di quanto sembri.
$$
	\begin{aligned}
	P\left( Y\geq \frac{1}{2}|X=0 \right)&=\int^1_{\frac{1}{2}} p(y|x=0)\,dy \overset{P. cond.}{=} \frac{2}{\pi}\int^1_{\frac{1}{2}} \frac{p_{XY}(x=0,y)}{p_{X}(x=0)}\, dy \\
	\text{calcolo la densità di} &\text{ probabilità marginale } p_{X}(x=0) : \\
	p_{x}(x=0)&=\int_{0}^1 p_{XY}(x=0,y)\,dy=\frac{2}{\pi}\int^1_{0}dy=\frac{2}{\pi}\\
	\implies P\left( Y\geq \frac{1}{2}|X=0 \right)&=\int^1_{\frac{1}{2}} \frac{2/\pi}{2/\pi}\,dy = \frac{1}{2}
	\end{aligned}
$$
E abbiamo ottenuto il risultato che ci aspettavamo.
Proviamo ora a rifare il calcolo in coordinate polari. Sappiamo che $\det J(r,\theta)=r$, per cui:
$$
	p_{r,\theta}(r.\theta)=\frac{2}{\pi}r
$$
La probabilità di trovarci sulla metà superiore del raggio diventa adesso:
$$
	\begin{aligned}
	P\left( r\geq \frac{1}{2}|\theta=\frac{\pi}{2} \right)&=\int^1_{\frac{1}{2}} p_{r\theta}\left(r,\theta=\frac{\pi}{2}\right) \, dr = \int^1_{\frac{1}{2}} \frac{p_{r\theta}(r=0,\theta)}{p_{r}(r=0)}\,dr\\
	p_{r}(r=0)&=\int^1_{0} p_{r\theta}\left( r,\theta=\frac{\pi}{2} \right)\,dr=\int_{0}^1 \frac{2}{\pi}r\,dr=\frac{1}{\pi}\\
	\implies P\left( r\geq \frac{1}{2}|\theta=\frac{\pi}{2} \right)&=\int^1_{\frac{1}{2}} \frac{2\pi/r}{1/\pi}\,dr = \int^1_{\frac{1}{2}} 2r \, dr = r^2|^1_{\frac{1}{2}}=\frac{3}{4}
	\end{aligned}
$$
Abbiamo ottenuto due probabilità diverse. Questo risultato è ovviamente paradossale. Proviamo ad investigarne la causa. Il problema è situato proprio nella misura nulla del raggio. Se consideriamo un intervallo attorno al raggio e lo mandiamo a 0, ci osserviamo che nelle 2 rappresentazioni diverse, gli intervalli che consideriamo sono profondamente diversi e dunque è diversa la probabilità.

![[Pasted image 20261008092344.png]]

Il modo di trattare questo paradosso è molto complesso e difficilmente in scenari reali ci capiterà di incontrare questi problemi. (Per curiosità vedere le $\sigma$-algebre).

**Lezione Associata:** [[4.Distribuzioni di Probabilità continue (di variabili aleatorie)]]