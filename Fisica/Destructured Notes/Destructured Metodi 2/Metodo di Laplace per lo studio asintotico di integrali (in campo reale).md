
**Essenziali:** [[Definizione di sviluppo asintotico]], [[Non-unicità di uno sviluppo asintotico]]

Spesso è possibile approssimare il risultato di alcuni integrali sfruttando degli sviluppi asintotici. Uno dei possibili metodi per farlo è il metodo di Laplace.

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
In questo germe di dimostrazione potrebbe sembrare che non si sia mai fatto uso della richiesta di massimo assoluto di $f$ in $0$. In realtà questa rischiesta è necessaria ogniqualvolta venga fatta l'equivalenza asintotica $\int^\infty_{0} \sim \int^a_{0}$. 
Ipotizziamo di avere un altro massimo assoluto di $f(x)$ in una regione compresa tra $0$ e $\infty$. Mandando $s\to \infty, ; s\in D$ troveremo  che il risultato dell'integrale $\int^\infty_{0}$ sarà dato in egual modo da 2 diversi picchi e l'equivalenza asintotica non varrà più per ogni valore di $a$.

![[Pasted image 20261108225555.png]]

**OSS:** l'altezza dei massimi scala linearmente con $s$, dunque, anche una piccola differenza tra il massimo assoluto gli altri massimi "li annichilisce" tutti tranne quello assoluto in $0$, per $s\to \infty$.

**Lezione Associata:** [[7. Sviluppi Asintotici]]