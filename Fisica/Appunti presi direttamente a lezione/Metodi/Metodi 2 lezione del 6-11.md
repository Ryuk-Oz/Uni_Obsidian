
Ogni valutazione asintotica è fatta per $s\in D$
Valutazione di integrali usando serie asintotiche.

$$
	I_{a}(s) = \int^a_{0} e^{ -sx } \, dx
$$
con $s \in \mathbb{C}$, $s\to \infty$, $s \in D$, $D=\left\{  s\; / \; |args|< \frac{\pi}{2}-\delta, \, \delta>0  \right\}$, voglio che all'infinito $s$ abbia una parte reale
![[Pasted image 20261102145722.png|508]]
$$
	I_{a}(s)= - \frac{e^{ -sx }}{s}|^{^a}_{_{0}} = \frac{1}{s}(1-e^{ -sa })
$$
Dunque:
$$
	I_{a}(s) \underset{s\to \infty}{\sim} \frac{1}{s} - \frac{1}{s }\left( o + \frac{o}{s} +\dots \right)\sim \frac{1}{s} \quad \forall a
$$
allora:
$$
	I_{a}(s) \underset{s\to \infty}{\sim} I(s) = \int^\infty_{0} e^{ -sx } dx \quad \forall a
$$
Cioè la coda dell'integrale è trascurabile.
Definiamo un ulteriore integrale:
$$
	J_{a}^{(n)}(s) = \int^a_{0} x^n e^{ -sx } \, dx = (-1)^n \frac{d^n}{ds^n} \int^a_{0} dx\, e^{ -sx } = (-1)^n \frac{d^n}{ds^n}\left\{  \frac{1}{s}-\frac{e^{ -sa }}{s}  \right\}\underset{s\to \infty}{\sim} \frac{n!}{s^{n+1}} \quad \forall a
$$
Con un ragionamento analogo a prima si ottiene:
$$
	J_{a}^{(n)}(s) \underset{s\to \infty, \; s\in D}{\sim} \int^\infty_{0} x^n e^{ -sx } \, dx = \frac{n!}{s^{n+1}}
$$
Posso fare più di così!

**Teorema**:
- Hp: $g(x)$ ammette trasformata di Laplace (cioè è localmente sommabile, cioè $\in L(a,b)$ 
  e $|e^{ -a x }g(x)|\in L$).
- Th: $\forall a>0$
$$
	\int_{a}^\infty e^{ -sx } g(x) \underset{\begin{aligned}
	&s\to \infty \\
	&s \in D
	\end{aligned}}{\sim} O(e^{ -sa })
$$
Dimostriamolo facendo un cambio di variabile: $x-a=y$, 
$$
	\int^\infty_{a} e^{ -sx } g(x) dx = \int^\infty_{0} dy\, e^{ -s(y+a) }g(y+a)=e^{ -sa } \underbrace{\int^\infty_{0} dy\, e^{ -sy }\tilde{g}(y)}_{\text{ è limitato perchè TL}} \underset{\begin{aligned}
	&s\to \infty \\
	&s \in D
	\end{aligned}}{\sim} Me^{ -sa }
$$
Unendolo ai risultati precedenti possiamo concludere che:
$$
	\int^\infty_{0} e^{ -sx }g(x)\, dx \underset{\begin{aligned}
	&s\to \infty \\
	&s \in D
	\end{aligned}}{\sim} \int^a_{0} e^{ -sx } g(x) dx
$$
La parte importante è solo l'intorno di zero, delle code mi importa poco.
Sviluppo $g(x)$ $x\to{0}^+$:
$$
	g(x) = \sum^\infty_{n=0} g_{n} x^{n+\nu} \quad \mathrm{Re}(\nu)>-1, \quad g_{0} \neq_{0}
$$
Sostituisco lo sviluppo nell'integrale:
$$
	\int^a_{0} e^{ -sx } \sum^\infty_{n=0} g_{n} x^{n+\nu} \, dx \sim \sum^\infty_{n=0} g_{n} \int^\infty_{0} e^{ -sx } x^{n+\nu} \, dx = \sum^\infty_{n=0} g_{n} \frac{\Gamma(n+\nu+1)}{s^{n+\nu+1}}
$$
Posso scambiare sempre serie e integrale quando faccio lo sviluppo asintotico (capisci perchè).
Quest'oggetto dipende soltanto da cosa fa $g$ nell'origine. Il motivo è che per $s\gg 1$ l'esponenziale è zero ovunque tranne che vicino all'origine e il contributo dentro l'integrale è dato unicamente da un intorno dell'origine.

**Teorema**;
- Hp: 
$$
  	I(s)= \int^a_{0} e^{ sf(x) } g(x) \, dx \quad a \in \mathbb{R}^+
  $$
  con $f(x)$ regolare in $[0,a]$, dunque $f$ è sviluppabile con Taylor: $f(x)=\sum^\infty_{n=0} f_{n}x^n$. 
  Ulteriormente imponiamo $f_{1}\equiv f'(0)<0$, è un massimo relativo. Ma io voglio che sia un massimo assoluto, allora impongo un'ulteriore condizione.
  $x=0$ massimo assoluto per $x \in [0,a]$: $\forall\varepsilon >0 \, \exists A<f(0) \; / \; f(x)<A \; \forall x\in[\varepsilon,a]$

  Per $g(x)$ vogliamo invece che $\exists \delta >0$ tale che $g(x)=\sum^\infty_{l=0} g_{l} x^{l+\nu}$ , $\mathrm{Re}(\nu)> -1$, $g_{0}\neq0$, 
  $\forall x\in I_{\delta}(0)$.

- Th:
$$
	I(s) \underset{\begin{aligned}
	&s\to \infty \\
	&s \in D
	\end{aligned}}{\sim} g_{0} \frac{e^{ sf(0) }}{|f_{1}|^{\nu+1}} \frac{\Gamma(\nu+1)}{s^{\nu+1}}\left( 1+O\left( \frac{1}{s} \right) \right)
$$
Dimostrazione:

posso riscrivere $I(s)$ nel seguente modo:
$$
\begin{aligned}
I(s)=&\int^a_{0} dx \, e^{ s\left( f_{0}+|f_{1}|x+\sum^\infty_{n=2} f_{n}x^n \right) } g(x) \\
=&\, e^{ sf_{0} } \int^a_{0} e^{ -s|f_{1}|x } A(x,s) g(x); \qquad A(x,s)=\exp\left[ \sum^\infty_{n=2} f_{n}x^n \right]\\
\underset{\begin{aligned}
	&s\to \infty \\
	&s \in D
	\end{aligned}}{\sim}& e^{ sf_{0} } \int^a_{0} dx\, e^{ -s|f_{1}|x } A(x,s) \sum^\infty_{n=0} g_{n} x^{n+\nu}
\end{aligned} 
$$

Il prodotto tra $A(x,s)$ e $g(x)$, sviluppando l'esponenziale:
$$
	A(x,s)g(x)= x^{\nu}[g_{0}+g_{1}x+g_{2}x^2+g_{0}f_{2}sx^2+g_{0}f_{3}sx^3+g_{3}x^3+\dots]
$$
Sostituisco nell'integrale:
$$
	I(x)\underset{\begin{aligned}
	&s\to \infty \\
	&s \in D
	\end{aligned}}{\sim} e^{ sf_{0} } \int^a_{0} e^{ -s|f_{1}|x }[g_{0}x^\nu+g_{1}x^{\nu+1}+g_{0}f_{2}sx^{2+\nu}+\dots]
$$
ho trovato una somma di integrali con la stessa forma di quelli che abbiamo appena studiato.
Dobbiamo capire quale tra questi dà il contributo maggiore.
$$
	\int^a_{0} e^{ -sx } x^{n+\nu} \, dx \sim \int^\infty_{0} e^{ -sx } x^{n+\nu} = \frac{\Gamma(n+\nu+1)}{s^{n+\nu+1}}
$$
L'ordine dominante è il termine per il quale l'esponente di $s$ è minore. Nel nostro caso tale termine corrisponde a $g_{0} x^\nu$.
$$
	I(x) \sim e^{ sf_{0} } g_{0}\int ^a_{0} dx e^{ -s|f_{1}|x }x^\nu = e^{ sf_{0} } g_{0} \frac{\Gamma(\nu+1)}{s^{\nu+1}|f_{1}|^{\nu+1}}
$$
Talvolta potrebbe servire sviluppare ad ordini successivi ma lo vederemo poi.
FAI RAGIONAMENTI SUL MAX DI $f$.

Ragionamenti analoghi si possono fare per qualunque intervallo finito. Devo poter fare lo stesso anche quando il massimo è in mezzo al cammino di integrazione.
Occupiamoci di questo caso.
$$
	I(t) = \int^b_{a} e^{ t f(x) } g(x) \, dx ; \qquad t\to \infty, t\in D
$$
**Teorema**:
- Hp: $\exists x_{0} \in [a,b] \, / \, x_{0}$ massimo relativo e assoluto per $f(x)$, cioè: $f'(x_{0})=0$ e 
  $\forall\varepsilon >0 \; \exists A, A<f(x_{0})\; / \; f(x)<A \, \forall x \not\in I_{\varepsilon}(x_{0})$.
  $f$ e $g$ regolari in $[a,b]$
- Th:
$$
	I(t) \underset{\begin{aligned}
	&t\to \infty \\
	&t \in D
	\end{aligned}}{\sim} \sqrt{ 2\pi } g(x_{0}) e^{ tf(x_{0}) } \frac{1}{\sqrt{ |g''(x_{0})| }} t^{-1/2} \left( 1+O\left( \frac{1}{t} \right) \right)
$$
Dimostrazione:
$f$ e $g$ regolari, allora posso svilupparle con taylor.
$$
	f(x) \sim f(x_{0})+\frac{1}{2} f''(x_{0})(x-x_{0})^2+\sum^\infty_{n=3} f_{n}(x-x_{0})^n
$$
$$
	g(x)\sim g(x_{0})+g'(x_{0})(x-x_{0})+\dots=\sum_{l=0}^\infty g_{l} (x-x_{0})^l
$$
Dunque:
$$
	I(t)=\int^b_{a} dx\, e^{ tf(x_{0}) } e^{ (t/2) f''(x_{0})(x-x_{0})^2 } e^{ t \sum^\infty_{n=3} f_{n} (x-x_{0})^n } \sum^\infty_{l=0} g_{l}(x-x_{0})^l
$$
Chiamiamo:
$$
	H(x,t) = e^{ t \sum^\infty_{n=3} f_{n} (x-x_{0})^n } \sum^\infty_{l=0} g_{l}(x-x_{0})^l
$$
A questo punto cambiando variabile, $x-x_{0}=w$ otteniamo:
$$
	I(t) = e^{ tf(x_{0}) } \int^{b-x_{0}}_{a-x_{0}} dw \, e^{ -(t/2)f''(x_{0})w^2 } \underbrace{H(x,t)}_{g_{0}+\sum^\infty_{l=1} h_{l}(t)w^l}
$$
Ho un integrale contenente un fattore gaussiano.
