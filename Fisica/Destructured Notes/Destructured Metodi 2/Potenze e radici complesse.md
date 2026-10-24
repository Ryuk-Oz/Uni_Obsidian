Occupiamoci ora dello studio di funzioni del tipo:
$$
	f(z)=z^\alpha \quad z\in \mathbb{C}\quad\alpha \in \mathbb{C}
$$
possiamo riscriverle come:
$$
	f(z)=e^{ \log z^\alpha }=e^{ \alpha \log z }
$$
Dunque possiamo immaginare sia una funzione polidroma. 
Supponiamo infatti di avere una funzione non polidroma $g(z)$. Occupiamoci dello studio di $\hat{g}(z)=g(\log z)$. Chiamiamo $argz=\theta$ e definizmo l'intervallo di variazione di $\theta$; $\theta_{0}<\theta\leq \theta_{0}+2\pi$.
$$
	\hat{g}(z)=g(\log |z|+i\theta+i 2\pi n)
$$
Studio cosa succede nell'ipotetico taglio.
![[Pasted image 20261004173203.png]]

$$
	\begin{aligned}
	\hat{g}_{n_{+}}&=g(\log |z|+i\theta_{0}+i 2\pi n)\\
	\hat{g}_{{n_{-}}}&=g(\log |z|+i\theta_{0}+i 2\pi+i 2\pi n)
	\end{aligned}
$$
In generale avrò che $\hat{g}_{n_{+}}\neq \hat{g}_{n_{-}}$, dunque avrò una polidromia, generalmente di ordine $\infty$.
Inoltre $\hat{g}_{n_{-}}=\hat{g}_{(n+1)_{+}}$ pertanto i fogli saranno incollati allo stesso modo che nella funzione $\log z$.
Ne concludiamo che generalmente, $\hat{g}=g(\log z)$ sarà una funzione polidroma con le stesse proprietà di $\log z$.

A questo punto lo studio di $z^\alpha$ appare molto più semplice.
Studiamo come si comporta la funzione sul foglio $n$-esimo.
$$
	z^\alpha_{|n}=e^{ \alpha(\log |z|)+i\theta+i 2\pi n }=|z|^\alpha e^{ i\alpha \theta }e^{ i\alpha 2\pi n }
$$
Chiamo $|z|=\rho$ e scelgo come foglio 0 l'intervallo $0\leq \theta<2\pi$.
$$
	\begin{aligned}
	z^\alpha_{|n_{+}}&=\rho^\alpha e^{ i\alpha 2\pi n }\\
	z^\alpha_{|n_{-}}&=\rho^\alpha e^{ i\alpha2\pi }e^{i \alpha 2\pi n  }\\
	\implies z^\alpha_{|n_{-}}-z^\alpha_{|n_{+}}&=\rho^\alpha e^{ i\alpha 2\pi n }(e^{ i \alpha 2\pi }+1)
	\end{aligned}
$$
La discontinuità smette di essere additiva e diventa moltiplicativa.

Ci sono alcuni casi in cui questo si semplifica notevolmente, ad esempio:

- $\alpha\in k\in \mathbb{Z}$ 
  $$
  	e^{ i 2\pi n \alpha }=1, \text{ perchè sto elevando ad un multiplo intero di } 2\pi
  $$
  lo stesso vale anche per $e^{ i 2\pi \alpha }$, dunque otteniamo che: 
$$
	z^\alpha_{|n_{-}}-z^\alpha_{|n_{+}}=\rho^\alpha\cdot 1 \cdot(1-1)=0
$$
  cioè non ho polidromia. Queste sono le funzioni che studiavamo a metodi 1.

- $\alpha \in \frac{p}{q} \in \mathbb{Q}$, numero razionale. 
  $$
  	\begin{aligned}
	f_{0}&= \rho^{p/q}e^{ i \frac{p}{q} \theta }\\
	f_{1}&=\rho^{\frac{p}{q}}e^{ i \frac{p}{q} \theta }e^{ i \frac{p}{q} 2\pi }=f_{0} e^{ i\frac{p}{q} 2\pi }\\
	f_{2}&=\rho^{\frac{p}{q}}e^{ i \frac{p}{q} \theta } e^{ i \frac{p}{q} 4\pi }=f_{0}e^{ i \frac{p}{q}4\pi }\\
	&.\\
	&.\\
	&.\\
	f_{q-1}&=\rho^{\frac{p}{q}}e^{ i \frac{p}{q} \theta } e^{ i\frac{p}{q} (q-1) 2\pi}\\
	f_{q}&=\rho^\frac{p}{q} e^{ i \frac{p}{q} \theta } e^{ i p 2\pi }=f_{0}
	\end{aligned}
  $$
  dopo $q$ giri ritorno al valore iniziale, dunque la polidromia è di ordine $q-1$ finito.

Cosa succede invece per $\alpha \in \mathbb{C}$?
Supponiamo ad esempio di voler studiare $1^i$.
Definiamo $z^i$. 
$$
	z^i_{|n}=e^{ i\log z }=e^{ i(\log |z|+i\theta+i 2\pi n) }=e^{ i\log |z| }e^{ -\theta }e^{ -2\pi n }
$$
La funione ha polidromia di ordine infinito e decresce esponenzialmente all'aumentare dei fogli.
Scegliamo per il foglio zero l'intervallo $0\leq \theta< 2\pi$. Pertanto avrò:
$$
	z=1 \to |z|=1, \, \theta=0
$$
$$
	1^i_{|n}=e^{ i 0 }e^{ 0 }e^{ -2\pi n }=e^{ -2\pi n }
$$
Ovviamnete il valore di $1^i$ varia in base al foglio su cui stiamo lavorando.
Proviamo ora a studiare $(-i)^i$.
$$
	z=-i\to |z|=1, \, \theta=\frac{3\pi}{2}
$$
$$
	(-i)^i_{|n}=e^{ -\frac{3}{2}\pi }e^{ -2\pi n } \to (-i)^i_{|0}=e^{ -\frac{3}{2}\pi }
$$
Proviamo ora a fare una scelta di argomenti differente: $-\pi<\tilde{\theta}\leq \pi$.
Con questa scelta otteniamo:
$$
	z=-i\to |z|=1, \theta=-\frac{\pi}{2}
$$
$$
	(-i)^i_{|n}=e^{ \pi/2 }e^{ -2\pi n }\to (-i)^i_{|0}=e^{ \pi/2 }
$$
Il risultato sul primo foglio è diverso nei due casi. Tuttavia, esiste sempre un valore di $n$ che mi restituisce lo stesso risultato. 
$$
	(-i)^i_{|1}=e^{ -\frac{3}{2}\pi }
$$
Cioè ho solo cambiato il piano di partenza, poi, una volta fissato questo, tutti i risultati sono sempre univoci, e questo vale anche per il punto all'$\infty$.

Così come per il logaritmo, anche per le potenze posso trovarmi ad avere più punti di diramazione.
Consideriamo ad esempio: 
$$
	\begin{aligned}
	\left( \frac{z-a}{z-b} \right)^\alpha &= e^{ \alpha \log \frac{z-a}{z-b}}= \exp[\alpha(\log |\frac{z-a}{z-b}|+i(\varphi_{a}-\varphi_{b})+i 2\pi n)]\\
	&=|\frac{z-a}{z-b}|^\alpha e^{ i\alpha(\varphi_{a}-\varphi_{b}) } e^{ i\alpha 2\pi n }
	\end{aligned}
$$
Per quanto studiato nel caso del logaritmo, questa funzione è polidroma con punti diramazione $z=\alpha$ e $z=\beta$ e una polidromia che dipende da $\alpha$.

Analogamente possiamo andare a studiare:
$$
	[(z-a)(z-b)]^\alpha=e^{ \alpha \log(z-a)(z-b) }=|(z-a)(z-b)|^\alpha e^{ i\alpha(\varphi_{a}+\varphi_{b}) }e^{ i\alpha 2\pi n }
$$
Questa è quasi uguale all'altro caso, con l'unica differenza che a questo giro si vanno a sommare gli angolib $\varphi_{a}$ e $\varphi_{b}$. Questo comporta che anche l'infinito sia un punto di diramazione.
I punti di diramazione sono dunque $z=a,\, z=b,\, z=\infty$.

Studiamo la polidromia attorno a questi punti.

Supponiamo che $\alpha=\frac{p}{q}$, numero razionale e proviamo a girare intorno ad $a$.
$$
	\begin{aligned}
	f_{0}&=|(z-a)(z-b)|^{p/q} e^{ i \frac{p}{q} (\varphi_{a}+\varphi_{b}) }\\
	f_{1}&=|(z-a)(z-b)|^{p/q} e^{ i \frac{p}{q} (\varphi_{a}+\varphi_{b}) }e^{ i \frac{p}{q} 2\pi }=f_{0}e^{ i \frac{p}{q}2\pi }\\
	\dots\\
	f_{q}&=|(z-a)(z-b)|^{p/q} e^{ i \frac{p}{q} (\varphi_{a}+\varphi_{b}) }e^{ ip 2\pi }=f_{0}
	\end{aligned}
$$
e troviamo polidromia di ordine $q-1$. La stessa cosa avviene in $b$.
Cosa succede se giro attorno a $\infty$?
$$
	f_{0}=|(z-a)(z-b)|^{p/q} e^{ i \frac{p}{q} (\varphi_{a}+\varphi_{b}) } \,\overset{giro}{\longrightarrow}\,|(z-a)(z-b)|^{p/q} e^{ i \frac{p}{q} (\varphi_{a}+\varphi_{b}) }e^{ i \frac{p}{q} -2\cdot 2\pi}
$$
Quando vado a girare intorno all'infinito sto girando sia intorno ad $a$ che a $b$ quindi ho un incremento doppio.

![[Pasted image 20261004193733.png]]

Ad esempio, per $q=5$ passo da $f_{0}\to f_{2}\to f_{4}\to f_{1}\to f_{3}\to f_{5}=f_{0}$
Per $q=6$ passo da $f_{0}\to f_{2}\to f_{4}\to f_{6}=f_{0}$
Dunque se $q$ è dispari ho polidromia di ordine $q-1$, se $q$ è pari ho polidromia di ordine $\frac{q}{2}-1$.
Nel caso in cui $q=2$ ho polidromia di ordine 0 e l'$\infty$ non è un punto di diramazione (questo non ci garantisce però che l'infinito non vada a causare problemi).


**Lezione Associata:** [[2.Funzioni polidrome]]