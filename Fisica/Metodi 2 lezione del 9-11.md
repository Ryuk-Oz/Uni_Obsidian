
Riprendiamo la lezione precedente.
L'obiettivo di oggi è calcolare:
$$
	I(t)=\int^b_{a} e^{ tf(x) } g(x)\, dx
$$
per $t\to \infty$ e $t \in D$ con $D$ costruito in modo che $s$ abbia sempre una parte reale all'infinito.
Ulteriormente abbiamo richiesto le seguenti ipotesi:
- $f(x)$ ha un massimo assoluto in $x_{0} \in [a,b]$, $f'(x)=0, \; f''(x_{0})>0$
- $f(x)$ è sviluppabile in serie di Taylor.
$$
	f(x)=f(x_{0})-\frac{1}{2}|f''(x_{0})|(x-x_{0})^2+\sum^\infty_{k=2} f_{k} (x-x_{0})^k
$$
- $g(x)$ è anch'esso sviluppabile in serie di Taylor:
$$
	g=\sum^\infty_{l=0}g_{l}(x-x_{0})^l
$$

Posso sostituire gli sviluppi nell'integrale per ottenere:
$$
	I(t)= e^{ tf(x_{0}) } \int^b_{a} dx\, e^{ -t/2\; |f''(x_{0})|(x-x_{0})^2} \underbrace{e^{ t\sum^\infty_{k=3} f_{k} (x-x_{0})^k } \sum_{l=0}^\infty g_{l}(x-x_{0})^l}_{H(t,x_{0})}
$$
Sviluppando $H(t,x_{0})$ e cambiando variabile $w=x-x_{0}$ ottengo:
$$
	I(t)=e^{ tf(x_{0}) } \int^{b-x_{0}}_{a-x_{0}} e^{ -t/2\; |f''(x_{0})|w^2 } \left( g_{0}+\sum^\infty_{l=1} h_{l}(t)w^l \right)
$$
Vorremmo mandare gli estremi di integrazione a infinito.
Facciamo un passo indietro e riconduciamoci al caso che già sappiamo studiare.
$$
	\begin{aligned}
	\int^\infty_{c} e^{ -t(y^2+c^2-c^2) } dy&=e^{ -tc^2 }\int^\infty_{c} e^{ -t(y^2-c^2) } dy\\
	&=\frac{e^{ -tc^2 }}{2} \int^\infty_{0} dx \frac{1}{\sqrt{ x^2-c^2 }} e^{ -tx }=O(e^{ -tc^2 })
	\end{aligned}
$$
Posso fare lo stesso ragionamento anche per l'intervallo $(-\infty,-c)$ (o lo vedo semplicemente sfruttando la parità).
La stessa cosa vale anche per una funzione $g(y)$ trasformabile con Laplace:
$$
	\int^\infty_{c} g(y)e^{ -t(y^2+c^2-c^2) } dy=\frac{e^{ -tc^2 }}{2}\underbrace{\int^\infty_{0} dx \frac{g(\sqrt{ x^2-c^2 })}{\sqrt{ x^2-c^2 }}e^{ -tx }}_{\text{è limitata perchè è una TL}} = O(e^{ -tc^2 })
$$
Dunque posso trascurare le cose anche per $I(t)$.
$$
	I(t) \underset{\begin{aligned}
	&t\to \infty\\
	&t \in D
	\end{aligned}}{\sim} e^{ tf(x_{0}) }\int^\infty_{-\infty} e^{ -t/2\; |f''(x_{0})|w^2 }(g_{0}+\cancel{h_{1}(t)w}+h_{2}(t)w^2+\dots)
$$
Posso svolgere singolarmente i vari termini.
L'intervallo è simmetrico, quindi le POTENZE DISPARI NON CONTRIBUISCONO.
Calcoliamo gli altri termini:
$$
	\begin{aligned}
	&\int^\infty_{-\infty} e^{ -tAw^2 } dw = \sqrt{ \frac{\pi}{tA} }\\
	&\int^\infty_{-\infty} e^{ -tAw^2 } w^2 dw = -\frac{d}{d(tA)} \sqrt{ \frac{\pi}{tA} }=+\frac{1}{2} \frac{\sqrt{ \pi }}{(tA)^{3/2}} =+\frac{1}{2} \sqrt{ \frac{\pi}{tA} } \frac{1}{tA}\\
	& \int^\infty_{-\infty} e^{ -tAw^2 } w^{2n} dw = (-1)^n \frac{d^n}{d(tA)^n}(-1)^n \frac{1}{2} \frac{3}{2} \frac{5}{2}\dots \frac{2n-1}{2} \sqrt{ \frac{\pi}{tA} } \frac{1}{(tA)^n}=\frac{(2n-1)!}{2^n} \sqrt{ \frac{\pi}{tA} } \frac{1}{(tA)^n}
	\end{aligned}
$$
Il termine dominante è chiaramente il primo. 
$$
	I(t) \underset{\begin{aligned}
	&t\to \infty\\
	&t\in D
	\end{aligned}}{\sim} e^{ tf(x_{0}) }\int^\infty_{-\infty} e^{ -t/2\; |f''(x_{0})|w^2 }(g_{0}+\cancel{h_{1}(t)w}+h_{2}(t)w^2+\dots) \sim g_{0} e^{ tf(x_{0}) } \sqrt{ \frac{2\pi}{t|f''(x_{0})|} }
$$

Facciamo un esempio:
$$
	I(\hat{t}) = \int^\pi_{0} e^{ \hat{t}\sin x } \sin x \, dx
$$
Studiamolo per $\hat{t}\to +\infty$ e $\hat{t}\to -\infty$.
**OSS:** per studiare $\hat{t}\to-\infty$ possiamo ragionare in questo modo:
$$
	\hat{t} \sin(x) = t(-\sin x),\qquad t=-\hat{t}
$$
e studio l'integrale per $t\to \infty$
$$
	I(t) = \int_{0}^\pi e^{ t(-\sin x) } \sin x\; dx
$$
Nei due casi troviamo rispettivamente:
- $\sin x$ ha un massimo in $\frac{\pi}{2}$
- $-\sin x$ ha 2 massimi in $0$ e $\pi$, che contribuiscono allo stesso modo. Per studiarlo posso sfruttare la simmetria rispetto a $\frac{\pi}{2}$.
$$
	I(t) = 2 \int^{\pi/2}_{0} e^{ t(-\sin x) } \sin x \; dx
$$
(PER CASA CALCOLA ESPLICITAMENTE TUTTO ATTORNO A $\pi$).
Iniziamo sviluppando il seno:
$$
	\sin(x) = \sum^\infty_{l=0} \frac{(-1)^l}{(2l+1)!} x^{2l+1}=x-\frac{1}{3!}x^3+ \frac{1}{5!} x^5+\dots
$$
Dunque:
$$
	I(t)= 2 \int^{\pi/2}_{0} e^{ -tx } e^{ -t\sum_{l=1}^\infty \frac{(-1)^l}{(2l+1)!} x^{2l+1} } \sum^\infty_{k=0} \frac{(-1)^k}{(2k+1)!} x^{2k+1}
$$
**PROBLEMA**: $\sin x$ è una funzione periodica che converge in tutto il piano. Quando mando l'intervallo a infinito prendendo TUTTA la serie, ho infiniti massimi ugualemente influenti. Per tale motivo devo troncare la serie prima di mandare l'intervallo a infinito! (La serie di potenze troncate non sarà più periodica).


Capiamo come troncare la serie. Sviluppiamo l'esponenziale con il pianpo terra ($g(x)$):
$$
	\left( 1+t\left( \frac{1}{3!} x^3-\frac{1}{5!}x^5+\dots\right)+\frac{t^2}{2} \left( \frac{1}{3!} x^3 -\frac{1}{5!}x^5+\dots \right)^2+ \dots\right)\cdot\left( x -\frac{1}{3!} x^3 +\frac{1}{5!} x^5 +\dots \right)
$$
RICORDANDOCI che: $\int e^{ -tx }x^n\sim \frac{1}{t^{n+1}}$, studiamo i vari ordini.
- Il termine dominante è $\frac{1}{t^2}$ e si ha troncando lo sviluppo a $x$.
- Il secondo ordine è $\frac{1}{t^4}$ e si ha troncando lo sviluppo a $-\frac{1}{3!}x^3+\frac{1}{3!}t x^4$
- ecc...
Dunque:
$$
	I(t) \underset{\begin{aligned}
	&t\to \infty\\
	&t \in D
	\end{aligned}}{\sim} 2\int^\infty_{0} dx\, e^{ -tx } \left( x-\frac{1}{6}x^3+\frac{1}{6}tx^4 \right)
$$
(PER CASA FAI L'ORDINE SUCCESSIVO).
$$
	= 2\int^\infty_{0} dx \, e^{ -tx }-\frac{1}{3} \int^\infty_{0} dx\, e^{ -tx } x^3 + \frac{t}{3} \int^\infty_{0} dx\, e^{ -tx } x^4
$$
Possiamo calcolare ognuno di questi termini in modo semplice, tramite le derivate.
$$
	\begin{cases}
	\int^\infty_{0} e^{ -tx } dx= \left[ \frac{e^{ -tx }}{x} \right]^\infty_{0} = \frac{1}{t} \\
	\int^\infty_{0} e^{ -tx } x\, dx = -\frac{d}{dt} \frac{1}{t} = \frac{1}{t^2} \\
	\int^\infty_{0} e^{ -tx } x^3 \, dx = -\frac{d^3}{dt^3} \frac{1}{t} =3! \frac{1}{t^4} \\
	\text{ecc}\dots
	\end{cases}
$$
Dunque:
$$
	I(t)\sim 2 \frac{1}{t^2}-\frac{1}{3} \frac{3!}{t^4}+ \frac{t}{3} \frac{4!}{t^5} = \frac{2}{t^2}+\frac{6}{t^4}+O\left( \frac{1}{t^6} \right)
$$
L'ordine successivo viene $\frac{90}{t^6}$ (questa roba ha 4 contributi!).


Studiamo ora il caso $\hat{t}\to{\infty}$. Chiamiamolo t per comodità.
$$
	I(t)=\int^\pi_{0} e^{ t\sin x } \sin x \, dx
$$
$\sin x$ ha un max in $\frac{\pi}{2}$.
Riscrivo $\sin x$ come:
$$
	\sin x = \cos\left( \frac{\pi}{2}-x \right)=1- \frac{1}{2} \left( x-\frac{\pi}{2} \right)^2+ \sum^\infty_{l=0} \frac{(-1)^l}{(2l)!}\left( x-\frac{\pi}{2} \right)^{2l}=1-\frac{1}{2} w^2+ \sum^\infty_{l=0} \frac{(-1)^l}{(2l)!}w^{2l}
$$
Sostituiamo nell'integrale:
$$
	I(t)=\int^{\pi/2}_{-\pi/2} dw \, e^{ t } e^{ -1/2\; t^2 }e^{ t \sum^\infty_{l=2}\frac{(-1)^l}{(2l)!}\left( w \right)^{2l} } \left( 1-\frac{1}{2}w^2+\frac{1}{4!}w^4+\dots \right)
$$
Dunque:
$$
	\begin{aligned}
	I(t) &\underset{t\to \infty}{\sim} e^{ t } \int^\infty_{-\infty} e^{ -t/2 \; w^2} \left( 1+\frac{t}{4!} w^4+\dots \right)\left( 1-\frac{1}{2}w^2+\dots \right) dw\\
	&= e^{ t }\left[ \int^\infty_{-\infty} e^{ -t/2 \; w^2 } dw+\frac{1}{2}\int^\infty_{-\infty} e^{ -t/2 \; w^2}w^2dw+\frac{t}{4!} \int^\infty_{-\infty} e^{ -t/2 \; w^2}w^4 dw+\dots \right]
	\end{aligned}
$$
Calcolando i vari termini derivando sotto il segno di integrale (fatto all'inizio della lezione di oggi), otteniamo:
$$
	\begin{aligned}
	I(t) &\underset{t\to \infty}{\sim} e^{ t }\left[ \sqrt{ \frac{2\pi}{t} }-\frac{1}{2} \frac{1}{2} \sqrt{ \frac{2\pi}{t} } \frac{2}{t}+ \frac{t}{6\cdot4} \frac{3}{4} \sqrt{ \frac{2\pi}{t} } \frac{4}{t^2} \right]\\
	&= e^{ t } \sqrt{ \frac{2\pi}{t} } \left( 1-\frac{1}{2} \frac{1}{t}+ \frac{1}{8} \frac{1}{t} \right)= e^{ t } \sqrt{ \frac{2\pi}{t} } \left( 1-\frac{3}{8} \frac{1}{t} \right)
	\end{aligned}
$$
FAI ORDINE SUCCESSIVO
a $+\infty$ e $-\infty$ gli andamenti sono significativamente diversi.


### Formula di stirling

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
	&= -1-\frac{1}{2}(y-1)^2 +\sum^\infty_{n=3} \frac{(-1)^n}{n} (y-1)^n
	\end{aligned}
$$
Sviluppiamo anche il termine al piano terra:
$$
	\frac{1}{y}= \frac{1}{(y-1)+1} = \sum^\infty_{k=0} (y-1)^k (-1)^k=1-(y-1)+(y-1)^2+\dots
$$
Mettendo tutti i0 pezzi insieme si ha:
$$
	\begin{aligned}
	\Gamma(t) &\underset{t\to \infty}{\sim} \int^{1+\delta}_{1-\delta} dy\, (\dots)=t^t \int^\delta_{-\delta} dw \; e^{ t \left( 1-1/2\; w^2+\sum_{n=3}^\infty \frac{(-1)^n}{n} w^n \right)} \sum^\infty_{l=0} (-1)^l w^l\\
	& \sim t^t e^{ -t } \int^\infty_{-\infty} e^{ -t/2\; w^2 }\left[ 1+t \left( -\frac{w^3}{3}+ \frac{w^4}{4}+\dots \right)+\frac{t^2}{2}\left( -\frac{w^3}{3}+\dots \right)^2\right]\cdot[1-w+w^2]
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
CONTROLLA CON CALMA I SEGNI (SU TUTTO STIRLING)
FINISCI A CASA.