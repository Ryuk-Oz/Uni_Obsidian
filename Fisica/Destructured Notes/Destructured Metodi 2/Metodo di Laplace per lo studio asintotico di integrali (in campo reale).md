
**Essenziali:** [[Definizione di sviluppo asintotico]], [[Non-unicità di uno sviluppo asintotico]]

**Indice:** [[Metodo di Laplace per massimo negli estremi di integrazione]], [[Metodo di Laplace per massimo in MEZZO agli estremi di integrazione]]

Spesso è possibile approssimare il risultato di alcuni integrali sfruttando degli sviluppi asintotici. Uno dei possibili metodi per farlo è il metodo di Laplace.

#### Massimo in un estremo di integrazione

Partiamo con un esempio elementare per poi enunciare alcuni teoremi di natura più generale.
$$
	I_{a}(s) = \int^a_{0} e^{ -sx } \, dx
$$
con $s \in \mathbb{C}$, $s\to \infty$, $s \in D$, $D=\left\{  s\in \mathbb{C}; \; |args|< \frac{\pi}{2}-\delta, \, \delta>0  \right\}$ (scelgo un dominio di questo tipo anzichè il semipiano reale, perchè voglio che all'infinito $s$ abbia sempre una parte reale).
![[Pasted image 20261102145722.png|508]]
$$
	I_{a}(s)= - \frac{e^{ -sx }}{s}|^{^a}_{_{0}} = \frac{1}{s}(1-e^{ -sa })
$$
Dunque:
$$
	I_{a}(s) \underset{s\to \infty, \; s \in D}{\sim} \frac{1}{s} - \frac{1}{s }\left( o + \frac{o}{s} +\dots \right)\sim \frac{1}{s} \quad \forall a
$$
Qua abbiamo sfruttato la proprietà degli sviluppi asintotici per cui lo sviluppo asintotico di $e^{ -z }z^n$ per $z\to \infty, \; z\in D$ è nullo.
Allora:
$$
	I_{a}(s) \underset{s\to \infty, \; s \in D}{\sim} I(s) = \int^\infty_{0} e^{ -sx } dx = \frac{1}{s} \quad \forall a
$$
Cioè la coda dell'integrale (la porzione che va da $a$ a $\infty$) è trascurabile per $s\to \infty$, $s\in D$ e qeusto vale $\forall a$. Nella figura questo risulta abbastanza chiaro.

![[Pasted image 20261108221124.png]]

Definiamo un ulteriore integrale:
$$
	J_{a}^{(n)}(s) = \int^a_{0} x^n e^{ -sx } \, dx = (-1)^n \frac{d^n}{ds^n} \int^a_{0} dx\, e^{ -sx } = (-1)^n \frac{d^n}{ds^n}\left\{  \frac{1}{s}-\frac{e^{ -sa }}{s}  \right\}\underset{s\to \infty}{\sim} \frac{n!}{s^{n+1}} \quad \forall a
$$
Con un ragionamento analogo a prima si ottiene:
$$
	J_{a}^{(n)}(s) \underset{s\to \infty, \; s\in D}{\sim} \int^\infty_{0} x^n e^{ -sx } \, dx = \frac{n!}{s^{n+1}}
$$
(integrando per parti l'integrale si verifica facilmente).

Ma posso fare più di così! Esistono infatti dei teoremi per studiare situazioni più generali.

**Teorema**:
- **Hp**: $g(x)$ ammette trasformata di Laplace (cioè è localmente sommabile, $\in L(a,b)$ 
  e $|e^{ -a x }g(x)|\in L$).
- **Th**: $\forall a>0$:
$$
	\int_{a}^\infty e^{ -sx } g(x) dx\underset{\begin{aligned}
	&s\to \infty \\
	&s \in D
	\end{aligned}}{\sim} O(e^{ -sa })
$$
Dimostriamolo facendo un cambio di variabile: $x-a=y$, 
$$
	\int^\infty_{a} e^{ -sx } g(x) dx = \int^\infty_{0} dy\, e^{ -s(y+a) }g(y+a)=e^{ -sa } \underbrace{\int^\infty_{0} dy\, e^{ -sy }\tilde{g}(y)}_{\text{ è limitato perchè è una TL}} \underset{\begin{aligned}
	&s\to \infty \\
	&s \in D
	\end{aligned}}{\sim} Me^{ -sa }
$$
Unendolo ai risultati precedenti possiamo concludere che:
$$
	\int^\infty_{0} e^{ -sx }g(x)\, dx \underset{\begin{aligned}
	&s\to \infty \\
	&s \in D
	\end{aligned}}{\sim} \int^a_{0} e^{ -sx } g(x) dx \underset{\begin{aligned}
	&s\to \infty\\
	&s \in D
	\end{aligned}}{\sim} O(e^{ -sa })
$$
La parte importante è solo l'intorno di zero, delle code mi importa poco.

Posso ottenere un risultato più preciso nel caso in cui sia possibile sviluppare $g(x)$ per $x\to{0}^+$ nel seguente modo:
$$
	g(x) = \sum^\infty_{n=0} g_{n} x^{n+\nu} \quad \mathrm{Re}(\nu)>-1, \quad g_{0} \neq{0}
$$
L'esponente complesso $\nu$ serve a includere anche funzioni $g(x)$ polidrome. (Chiedi a Frau)
Sostituisco lo sviluppo nell'integrale:
$$
	\int^a_{0} e^{ -sx } \sum^\infty_{n=0} g_{n} x^{n+\nu} \, dx \sim \sum^\infty_{n=0} g_{n} \int^\infty_{0} e^{ -sx } x^{n+\nu} \, dx = \sum^\infty_{n=0} g_{n} \frac{\Gamma(n+\nu+1)}{s^{n+\nu+1}}
$$
Posso sempre scambiare sempre serie e integrale quando faccio lo sviluppo asintotico, infatti $\int^\infty_{0}\sim \int^a_{0}\; \forall a$, prendendo $a$ arbitrariamente piccolo posso mandare il raggio di integrazione a $0$ e dunque anche serie divergenti (raggio di convergenza nullo) "convergono uniformemente" sotto il segno di integrale.
Quest'oggetto dipende soltanto da cosa fa $g$ nell'origine. Intuitivamente posso motivarlo nel seguente modo: per $s\gg 1$ l'esponenziale è zero ovunque tranne che vicino all'origine e il contributo dentro l'integrale è dato unicamente da un intorno dell'origine.

**Teorema**:
- **Hp**: 
$$
  	I(s)= \int^a_{0} e^{ sf(x) } g(x) \, dx \quad a \in \mathbb{R}^+
  $$
  con $f(x)$ regolare in $[0,a]$, dunque $f$ è sviluppabile con Taylor: $f(x)=\sum^\infty_{n=0} f_{n}x^n$. 
  Ulteriormente imponiamo $f_{1}\equiv f'(0)<0$, massimo relativo. Vogliamo che sia un massimo assoluto, imponiamo dunque un ulteriore condizione.
  $x=0$ massimo assoluto per $x \in [0,a]$: $\forall\varepsilon >0 \, \exists A<f(0) \; / \; f(x)<A \; \forall x\in[\varepsilon,a]$

  Per $g(x)$ vogliamo invece che $\exists \delta >0$ tale che $g(x)=\sum^\infty_{l=0} g_{l} x^{l+\nu}$ , $\mathrm{Re}(\nu)> -1$, $g_{0}\neq0$, 
  $\forall x\in I_{\delta}(0)$.

- **Th**:
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
ho trovato una somma di integrali con la stessa forma di quelli che abbiamo appena studiato:
$$
	\int^a_{0} e^{ -sx } x^{n+\nu} \, dx \sim \int^\infty_{0} e^{ -sx } x^{n+\nu} = \frac{\Gamma(n+\nu+1)}{s^{n+\nu+1}}
$$
Dobbiamo capire quale tra questi dà il contributo maggiore.
L'ordine dominante è il termine per il quale l'esponente di $s$ è minore. Nel nostro caso tale termine corrisponde a $g_{0} x^\nu$.
$$
	I(x) \sim e^{ sf_{0} } g_{0}\int ^a_{0} dx e^{ -s|f_{1}|x }x^\nu = e^{ sf_{0} } g_{0} \frac{\Gamma(\nu+1)}{s^{\nu+1}|f_{1}|^{\nu+1}}
$$
Talvolta potrebbe servire sviluppare ad ordini successivi ma lo vederemo poi.
In questo germe di dimostrazione potrebbe sembrare che non si sia mai fatto uso della richiesta di massimo assoluto di $f$ in $0$. In realtà questa rischiesta è necessaria ogniqualvolta venga fatta l'equivalenza asintotica $\int^\infty_{0} \sim \int^a_{0}$. 
Ipotizziamo di avere un altro massimo assoluto di $f(x)$ in una regione compresa tra $0$ e $\infty$. Mandando $s\to \infty, ; s\in D$ troveremo  che il risultato dell'integrale $\int^\infty_{0}$ sarà dato in egual modo da 2 diversi picchi e l'equivalenza asintotica non varrà più per ogni valore di $a$.

![[Pasted image 20261108225555.png]]

**OSS:** l'altezza dei massimi scala linearmente con $s$, dunque, anche una piccola differenza tra il massimo assoluto gli altri massimi "li annichilisce" tutti tranne quello assoluto in $0$, per $s\to \infty$.

#### Massimo in mezzo

Il metodo di Laplace si può facilmente generalizzare per funzioni che non hanno il massimo in uno dei due estremi di integrazione, ma il massimo assoluto cade tra gli estremi. In questo caso dovremo richiedere l'annullamento della derivata e questo avrà delle conseguenze sullo sviluppo.

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
	& \int^\infty_{-\infty} e^{ -tAw^2 } w^{2n} dw = (-1)^n \frac{d^n}{d(tA)^n}(-1)^n \frac{1}{2} \frac{3}{2} \frac{5}{2}\dots \frac{2n-1}{2} \sqrt{ \frac{\pi}{tA} } \frac{1}{(tA)^n}=\frac{(2n-1)!!}{2^n} \sqrt{ \frac{\pi}{tA} } \frac{1}{(tA)^n}
	\end{aligned}
$$
Il termine dominante è chiaramente il primo. 
$$
	I(t) \underset{\begin{aligned}
	&t\to \infty\\
	&t\in D
	\end{aligned}}{\sim} e^{ tf(x_{0}) }\int^\infty_{-\infty} e^{ -t/2\; |f''(x_{0})|w^2 }(g_{0}+\cancel{h_{1}(t)w}+h_{2}(t)w^2+\dots) \sim g_{0} e^{ tf(x_{0}) } \sqrt{ \frac{2\pi}{t|f''(x_{0})|} }
$$

#### Esempio di applicazione del metodo di Laplace

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
	\sin x = \cos\left( \frac{\pi}{2}-x \right)=1- \frac{1}{2} \left( x-\frac{\pi}{2} \right)^2+ \sum^\infty_{l=2} \frac{(-1)^l}{(2l)!}\left( x-\frac{\pi}{2} \right)^{2l}=1-\frac{1}{2} w^2+ \sum^\infty_{l=2} \frac{(-1)^l}{(2l)!}w^{2l}
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
L'ordine successivo, a meno di errori di conto, dovrebbe essere $-\frac{15}{228} \frac{1}{t^2}$.
a $+\infty$ e $-\infty$ gli andamenti sono significativamente diversi.

**Lezione Associata:** [[7. Sviluppi Asintotici]]