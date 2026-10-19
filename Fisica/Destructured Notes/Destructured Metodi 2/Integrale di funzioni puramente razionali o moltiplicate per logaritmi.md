
**Prerequisito:** [[Funzione logaritmo]]

L'ultima classe di integrali che possiamo calcolare sfruttando le proprietà delle funzioni polidrome è quella degli integrali di funzioni puramente razionali (laddove non sia possibile calcolarli facendo uso di metodi tradizionali).
$$
	I=\int^b_{a} dx \, R(x)\quad a,b \in \mathbb{R}
$$
Come sempre studiamo per prima cosa l'esistenza dell'integrale. Perchè l'integrale esista la funzione $R(x)$ non deve avere poli $\in(a,b)$. Inoltre, per $x\to a$ dobbiamo avere $R(x)\sim A(x-a)^k$ con $k>-1$, e idem per $b$.

A questo punto consideriamo la funzione ausiliaria in campo complesso:
$$
	J=\oint_{\Gamma}dz\, R(z)\log\left( \frac{z-a}{b-z} \right)
$$
Il logaritmo "perde" sempre contro la potenza, dunque l'integrale converge.
Come al solito, scegliamo il taglio sul cammino di integrazione, e come abbiamo imparato per situazioni simili a questa, andiamo a scegliere come $\Gamma$ il cammino ad "osso di cane".

![[Pasted image 20261018180059.png]]

In questo modo possiamo calcolare $J$ come somma dei residui di $f(z)=R(z)\log\left( \frac{z-a}{b-z} \right)$.
Inoltre, l'integrale converge abbastanza velocemente da annullarsi sui cerchi e restiamo con:
$$
	J=\int^b_{a} dz\,(f_{+}(z)-f_{-}(z))
$$
Occupiamoci di calcolare $f_{-}$ ed $f_{+}$
$$
	\begin{cases}
	f_{+}=R(z)\left( \log | \frac{z-a}{b-z}|+i(\varphi_{a}-\varphi_{b})+i 2\pi n \right)\underset{z_{+}\to x}{\to} R(x)\left( \log\left( \frac{x-a}{b-x} \right)+i 2\pi n \right) \\
	f_{-}=R(z)\left( \log | \frac{z-a}{b-z}|+i(\varphi_{a}-\varphi_{b})+i 2\pi n \right)\underset{z_{-}\to x}{\to}R(x)\left( \log\left( \frac{x-a}{b-x} \right)+i 2\pi+i 2\pi n \right)
	\end{cases}
$$
Dunque:
$$
	J=\int^b_{a}(-i 2\pi)R(x)\, dx=-i2\pi \,I \implies I=-\sum_{\text{tutti}}\text{Res}\left[ R(z)\log\left( \frac{z-a}{b-z} \right) \right]
$$
Lo stesso trucco si può applicare al caso in cui gli estremi di integrazione sono $(0,\infty)$, semplicemente uso $\log z$ e la curva con 2 cerchi concentrici del primo caso preso in appello.

In maniera molto simile possiamo anche andare a studiare integrali di natura notoriamente più complessa:
$$
	I=\int^\infty_{0} dx R(x)\log x
$$
Questa volta scegliamo come integrale complesso ausiliario:
$$
	J=\oint dz\,R(z)\log^2(z)
$$
Analogamente a prima, posso calcolare $J$ come somma dei residui, oppure come:
$$
	J=\int^\infty_{0} dz\, (f_{+}(z)-f_{-}(z))
$$
Questa volta troviamo:
$$
	\begin{cases}
	f_{+}=R(x)(\log x+i\varphi )(\log x+i\varphi)\underset{z_{+}\to x}{\to}R(x)\log^2(x) \\
	f_{-}\underset{z_{-}\to x}{\to}R(x)(\log(x)+i 2\pi)^2=R(x)(\log^2(x)+i 4\pi \log(x)-4\pi^2)
	\end{cases}
$$
dunque:
$$
	f_{+}-f_{-}=R(x)(4\pi^2-i 4\pi \log(x))
$$
Chiamando $I^0=\int^\infty_{0}R(x)\,dx$ otteniamo:
$$
	J=4\pi^2I^0-i 4\pi I
$$
Da cui:
$$
	I=\frac{4\pi^2I^0-J}{4\pi i}=\frac{4\pi^2I_{0}-2\pi i\sum_{\text{tutti}}\text{Res}[R(z)\log^2(z)]}{4\pi i}
$$
In questo modo possiamo andare a calcolare iterativamente integrali della forma:
$$
	I=\int^\infty_{0}dx\,R(x)\log^n(x)
$$
**Osservazione finale utile per non sbagliare**:
Per funzioni polidrome la somma di tutti i residui non è mai nulla (anche sommando su tutta la superficie di Riemann), perchè il mio cammino di integrazione dovrà necessariamente attraversare il taglio. Si può ugualmente definire una quantità che si annulla se sommatta su tutta la superficie, ma non ce ne occuperemo adesso.