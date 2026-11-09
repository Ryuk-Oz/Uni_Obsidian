
Consideriamo una successione $\{ \varphi_{l}(z) \}$, $l=0,1,\dots$ regolari in $D$.
Diciamo che $\{ \varphi_{l}(z) \}$ è una successione asintotica per $z\to z_{0}$ $z\in D$, $z_{0}\in[D]$ se:
$$
	\varphi_{n}(z)=o(\varphi_{n-1}(z))
$$
Achtung: il punto $z_{0}$ che considero non è accessorio!

Esempi di successioni asintotiche usate comunemente:
$\varphi_{l}=(z-z_{0})^l g(z)$ è una successione asintotica per $z\to z_{0}$.
$\varphi_{l}=\frac{g(z)}{z^l}$ è una successione asintotica per $z\to\infty$.

A questo punto posso definire una serie asintotica:
$$
	f(z)\underset{\underset{z\in D}{z\to z_{0}}}{\sim}\sum^\infty_{l=0} a_{l} \,\varphi_{l}(z)
$$
se:
1. $\{ \varphi_{l}(z) \}$ è una successione asintotica per $z\to z_{0}$, $z\in D$
2. Il resto n-esimo:
$$
	R_{n}(z)=f(z)-\sum_{l=0}^{n-1} a_{l}\, \varphi_{l}(z)
$$
   è tale per cui: $R_{n}(z)= o(\varphi_{n}(z))$ per $z\to z_{0}$, $z\in D$.
Formalmente è più corretto scrivere $f(z)$ come una somma discreta più il resto n-esimo, in quanto la serie in se per se potrebbe non convergere.

Facciamo un esempio noto, la trasformata di Laplace.
$$
	F(s)=\mathcal{L}_{s}(f)=\int^\infty_{0} e^{ -sx } f(x) dx \qquad \text{analitica per } \mathrm{Re}(s)>\alpha_{0}
$$
Ricordiamo che:
$\mathcal{L}_{s}(f')=s\mathcal{L}_{s}(f)-f(0)$, da cui troviamo:
$$
	\mathcal{L}_{s}(f^{(n)})=s^n \underbrace{\mathcal{L}_{s}(f)}_{F(s)}-f(0)s^{n-1}-f'(0)s^{n-2}-\dots f^{(n-1)}(0)
$$
Pertanto posso riscrivere $F(s)$ come uno sviluppo asintotico:
$$
	F(s)=\frac{f(0)}{s}+\frac{f'(0)}{s^2}+\dots \frac{f^{(n-1)}(0)}{s^n}+\frac{1}{s^{n}} \mathcal{L}_{s}(f^{(n)}) \sim \sum^\infty_{l=0} \frac{f^{(l)}(0)}{s^{l+1}} \quad \text{per } s\to \infty
$$
ovviamente $s\to \infty$ dalla porzione di piano in cui $F(s)$ è definita ($\mathrm{Re}(s)>\alpha_{0}\equiv D$).
**Oss:** posso riscrivere $\mathcal{L}_{s}(f^{(n)})$ come:
$$
	\mathcal{L}_{s}(f^{(n+1)}) = s\mathcal{L}_{s}(f^{(n)})-f^{(n)}(0)\implies \mathcal{L}_{s}(f^{(n)})= \frac{\mathcal{L}_{s}(f^{(n+1)}+f^{(n)}(0)}{s}
$$
Dunque concludiamo che $\frac{\mathcal{L}_{s}(f^{(n)})}{s^n}=o(s^{-n})$ e lo sviluppo asintotico è legittimo.

Facciamo un esempio concreto:
$$
	f(x)=\frac{1}{1+x}=\sum^\infty_{n=0} (-1)^n x^n =\sum^\infty_{n=0} \frac{1}{n!} \left( \frac{d^nf}{dx^n} \right)_{0} x^n
$$
$f^{(n)}(0)=n!(-1)^n$, dunque:
$$
	F(s)\sim \sum^\infty_{l=0} \frac{(-1)^nn!}{s^{n+1}} \qquad \text{per } s\in D, \,s\to \infty
$$
La serie chiaramente non converge per $s\to \infty$.
Verifichiamo se sia possibile o meno scriverne uno sviluppo asintotico cioè se:
$$
	R_{n}(s)=\frac{\mathcal{L}_{s}(f^{(n)})}{s^n}\sim o\left( \frac{1}{s^n} \right)
$$
Sfruttando la definizione di trasformata di Laplace:
$$
	R_{n}(s)=\frac{1}{s^n}\int^\infty_{0} dx\, e^{ sx } \frac{(-1)^nn!}{(1+x)^{n+1}}=(-1)^nn!\int^\infty_{0}dx\, \frac{e^{ sx }s}{(s+sx)^{n+1}}
$$
Mi metto sull'asse reale e faccio un cambio di variabile, $s\in \mathbb{R}_{+}$, $s>\alpha_{0}$. Sia $sx=y$.
$$
	R_{n}(s)=(-1)^n n! \int^\infty_{0} dy\, \frac{e^{ -y }}{(s+y)^{n+1}}
$$
Posso maggiorarla:
$$
	|R_{n}(s)|\leq n! \int^\infty_{0} dy\, \frac{e^{ -y }}{|(s+y)^{n+1}|}\leq \frac{n!}{s^{n+1}} \int^\infty_{0} e^{ -y }dy
$$
Quanto è legittimo prendere $s\in \mathbb{R}_{+}$? Prendessi $s$ complesso, andrei a integrare su una retta inclinata, ma per $\mathrm{Re}(s)>\alpha_{0}$ l'argomento dell'integrale è analitico allora posso sempre deformare questa retta sulla retta reale. (Cioè posso continuare analiticamente l'integrale che abbiamo appena calcolato su tutto $D$)

**OSS:** Per serie divergenti non è detto che prendendo più termini la precisione aumenti, fissato $z$, vicino a $z_{0}$, aumentando il valore di $n$ la precisione aumenterà fino ad un certo punto, oltre il quale inizierà a divergere. Al contrario, fissato $n$, per $z\to z_{0}$ la precisione continuerà ad aumentare.
Esiste un $n$ ottimale che minimizza l'errore e oltre il quale la precisione inizia a calare.

Se fisso $n$ e mi avvicino a $z_{0}$, avrò un numero finito di $a_{k}$ che cresceranno (spesso con andamento fattoriale) fino a fermarsi ad $a_{n}$, indipendentemente da quanto io sia vicino a $z_{0}$. Al contrario i termini del tipo $(z-z_{0})^k$ diventeranno sempre più piccoli più mi avvicino a $z_{0}$.
Quindi la precisione della mia stima aumenterà.

Se invece fisso $z$ e aumento $n$, se è vero che i termini $(z-z_{0})^n$ diventeranno semprè più piccoli all'aumentare di $n$, d'altra parte è anche vero che i termini $a_{n}$ diventeranno sempre più grandi. Ad un certo punto i termini $a_{n}$ inizieranno a crescere più velocemente di quanto i termini $(z-z_{0})^n$ non diminuiscano e la serie andrà a divergere.
Quindi la precisione della mia stima inizierà a diminuire dopo un certo $n$.

Quando vado a calcolare il resto, facendo il limite $z\to z_{0}$, i coefficienti $a_{n}$ li andò a trattare come costanti e non influeranno sul risultato del limite, motivo per cui continuerò ad avere $R_{n}=o(\varphi_{n-1})$.

Qual è il numero ottimale di termini (nell'esempio che abbiamo appena svolto)?
$$
	|a_{n}|=\frac{n!}{s^{n+1}}=\frac{\sqrt{ 2\pi n }e^{ -n }n^n}{s^{n+1}}
$$
Cerchiamo il punto stazionario di questo coefficiente:
$$
	\partial_{n} \frac{n!}{s^{n+1}}=\frac{(\partial_{n}n!)s^{n+1}-n!\partial_{n}s^{n+1}}{s^{n+2}}=0
$$
Calcoliamo le derivate:
$$
	\partial_{n}s^{n+1}=s^{n+1}\log s \qquad \partial_{n}n^n=\partial _{n} e^{ n\log n }=n^n(\log n +1)
$$
Dunque:
$$
	\sqrt{ 2\pi } \partial_{n}(n^{1/2} e^{ -n } n^n)=\sqrt{ 2\pi }n^{1/2}n^n e^{ n }\left\{  \frac{1}{2}n^{-1}-1+\log n-1  \right\}=n!\left( \frac{1}{2n}+\log n \right)
$$
Allora:
$$
	\partial_{n}|a_{n}|=\frac{1}{2n}+\log n-\log s=0 \qquad \text{cioè} \qquad n_{0}e^{ 1/2n_{0} }\sim s
$$
per $n\to \infty$ trovo: $n_{0}\sim s$.
Come faccio a sapere se questo sia proprio un minimo? Posso verificarlo velocemente nel seguente modo:
$$
	\frac{(n-1)!}{s^n}> \frac{n!}{s^{n+1}}\quad \text{e}\quad 1>\frac{n}{s} \quad \text{per} \quad n<s
$$
cIoè $|a_{n}|$ è decrescente.


**Lezione Associata:** [[7. Sviluppi Asintotici]]