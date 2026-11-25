**Essenziale:** [[4.Funzione Gamma di Eulero]]

Parto dalla funzione $\Gamma$:
$$
	\Gamma(t)= \int^\infty_{0} e^{ -x } x^{t-1} dx
$$
Vogliamo studiarla per $t\to \infty$, $t \in D$.
Cambiamo variabile: $x=ty$, $dx = t dy$, $t \in \mathbb{R}_{+}$.
$$
		\Gamma(t) = \int^\infty_{0} t\,dy \; e^{ -ty } (ty)^t \frac{1}{ty} = t^t \int^\infty_{0} dy\; e^{ -ty } \underbrace{e^{ t\log y }}_{y^t} \frac{1}{y} = t^t \int^\infty_{0} dy\, \frac{1}{y} e^{ tf(y) }
$$
con $f(y)= \log y -y$.
Dove si trova il massimo di $\log y-y$?
$$
	f'(y)= \frac{1}{y}-1 = 0 \implies \text{Massimo in } x=1
$$
$$
	f''(y)=-\frac{1}{y^2},\qquad f''(1)=-1<0\quad \text{come richiesto nelle Hp}
$$
Sviluppiamo $f(y)$:
$$
	\log(1+w) = -\sum^\infty_{n=1} \frac{(-1)^n}{n} w^n
$$
$$
	\log y = \log(1+(y-1)) = -\sum^\infty_{n=1} \frac{(-1)^n}{n} (y-1)^n=(y-1)-\frac{1}{2}(y-1)^2+\frac{1}{3}(y-1)^3+\dots
$$
Dunque:
$$
	\begin{aligned}
	f(y) = \log y-y &= \cancel{(y-1)}-\frac{1}{2}(y-1)^2+\frac{1}{3}(y-1)^3+\dots-(y-1)-1\\
	&= -1-\frac{1}{2}(y-1)^2 -\sum^\infty_{n=3} \frac{(-1)^n}{n} (y-1)^n
	\end{aligned}
$$
Sviluppiamo anche il termine al piano terra:
$$
	\frac{1}{y}= \frac{1}{(y-1)+1} = \sum^\infty_{k=0} (y-1)^k (-1)^k=1-(y-1)+(y-1)^2+\dots
$$
Mettendo tutti i pezzi insieme si ha:
$$
	\begin{aligned}
	\Gamma(t) &\underset{t\to \infty}{\sim} \int^{1+\delta}_{1-\delta} dy\, (\dots)=t^t \int^\delta_{-\delta} dw \; e^{ t \left( 1-1/2\; w^2-\sum_{n=3}^\infty \frac{(-1)^n}{n} w^n \right)} \sum^\infty_{l=0} (-1)^l w^l\\
	& \sim t^t e^{ -t } \int^\infty_{-\infty} e^{ -t/2\; w^2 }\left[ 1+t \left( \frac{w^3}{3}- \frac{w^4}{4}+\dots \right)+\frac{t^2}{2}\left( +\frac{w^3}{3}-\dots \right)^2\right]\cdot[1-w+w^2]
	\end{aligned}
$$
Prendendo solo il termine dominante abbiamo:
$$
	\Gamma(t) \sim t^t e^{ -t } \int^\infty_{-\infty} dw\, e^{ -t/2\; w^2 }= t^t e^{ -t } \sqrt{ \frac{2\pi}{t} }
$$
Prendiamo anche l'ordine successivo:
$$
		\Gamma(t) \sim t^t e^{ -t } \int^\infty_{-\infty} dw\, e^{ -t/2\; w^2 }\left( 1+w^2-t w^4\left( \frac{1}{4}+\frac{1}{3} \right) +\frac{t^2}{18}w^6\right)
$$
Svolgendo tutti i conti si arriva a dire che:
$$
	\Gamma(t)\sim t^t e^{ -t } \sqrt{ \frac{2\pi}{t} }\left[ 1+\frac{1}{12t} \right]
$$
Ora possiamo sviluppare il fattoriale.
$$
	n! = \Gamma(n+1)=n\Gamma(n)\sim n^n e^{ -n } \sqrt{ 2\pi n }\left[ 1+\frac{1}{12n} \right]
$$
che è proprio la formula di stirling al primo ordine.

**Lezione Associata:** [[7. Sviluppi Asintotici]]