
**Prerequisiti:** [[Definizione della Beta di Eulero]]

Utilizzando la funzione $B$ di eulero è possibile fornire una formulazione alternativa della funzione $\Gamma$
Partiamo dalla definizione standard e facciamo il cambio di variabile $t=y^2$.
$$
	\Gamma(z)=\int^\infty_{0} dt\, t^{z-1} e^{ -t } \underset{t=y^2}{=} \int^\infty_{0} 2y \, dy\, y^{2z-2} e^{ -y^2 }=2\int^\infty_{0} dy \, e^{ -y^2 } y^{2z-1}
$$
A questo punto posso andare a riscrivere $\Gamma(z)\Gamma(u)$ usando questa forma.
$$
	\begin{aligned}
	\Gamma(z)\Gamma(u) &= 4\int^\infty_{0} dy \int^\infty_{0} dx \, e^{ -(x^2+y^2) } y^{2z-1} x^{2u-1}\\
	\text{cambio}& \text{ variabile:} \quad x=\rho \cos \theta \quad y=\rho \sin \theta \\
	&=4\int^\infty_{0} d\rho\,\rho \int^{\pi/2}_{0} d\theta\, e^{ -\rho^2 } \rho^{2(z+u)-2} (\cos \theta)^{2u-1} (\sin \theta)^{2z-1}=\\
	&=2\underbrace{\int^\infty_{0}d\rho \, e^{-\rho^2  }\rho^{2(z+u)-1}}_{\Gamma(z+u)} \, B(z,u)
	\end{aligned}
$$
E siamo riusciti a riscirvere la funzione $B$ in funzione di $\Gamma$.
$$
	\implies B(z,u)=\frac{\Gamma(z)\Gamma(u)}{\Gamma(z+u)}
$$
(Questa roba ha un'interpretazione probabilistica?)
Dunque la funzione $B(u,z)$ ha poli semplici in $z=-n$ e $u=-n$ con $n\in \mathbb{N}$ quando continuata al di fuori del proprio dominio di analiticità.

Sfruttiamo questo risultato per dare ancora una definizione di $\Gamma(z)$.
$$
	\Gamma(z)\Gamma(1-z)=B(z,1-z)=\int^1_{0} dt\, t^{z-1} (1-t)^{-z} = \int^1_{0} dt\, \frac{1}{t} \left( \frac{t}{1-t} \right)^z = \frac{\pi}{\sin \pi z}
$$
L'ultimo integrale lo abbiamo calcolato sfruttando le funzioni polidrome, è l'integrale di una funzione razionale per una potenza complessa.
So calcolare $\frac{\pi}{\sin \pi z}$ su tutto il piano complesso, quindi ho trovato un'ulteriore continuazione analitica di $\Gamma$.
___
$$
	\Gamma(z)=\frac{\pi}{\sin \pi z} \frac{1}{\Gamma(1-z)}, \qquad \mathrm{Re}(z)<1
$$
___
Questa forma ritrova ovviamente gli stessi poli e gli stessi residui che troveremmo con le altre continuazioni.

Questa formulazione è però utile per altri due motivi.
1. Scrivendo 
$$
   	\frac{1}{\Gamma(z)}=\frac{1}{\pi} \Gamma(1-z)\sin \pi z
   $$
   Abbiamo il prodotto tra una funzione che ha poli semplici negli interi positivi ed una funzione che ha zeri semplici negli interi positivi, pertanto $\Gamma(z)$ non si annulla mai perchè $\frac{1}{\Gamma(z)}$ è una funzione intera
2. Possiamo usare questa formulazione per calcolare il valore di $\Gamma$ per seminiteri 
   $$
   	\Gamma\left( \frac{1}{2} \right)\Gamma\left( \frac{1}{2} \right)=\left( \Gamma\left( \frac{1}{2} \right) \right)^2=\pi \implies \Gamma\left( \frac{1}{2} \right)=\sqrt{ \pi }
   $$
   Da qua possiamo poi generalizzare a un qualunque semiintero positivo:
$$
	\Gamma\left( n+\frac{1}{2} \right)=\frac{(2n-1)!!}{2^n} \sqrt{ \pi }
$$
   Dove col doppio puntoesclamativo intendiamo il semifattoriale. In questo modo sappiamo calcolare in maniera comoda il "fattoriale" di seminteri.
   Possiamo estendere questa argomentazione anche a seminteri negativi.
   Ricordando $\Gamma(z+1)=z\Gamma(z)$ possiamo scrivere:
$$
	\left( -\frac{1}{2} \right)\Gamma\left( -\frac{1}{2} \right)=-\Gamma\left( -\frac{1}{2}+1 \right)=\Gamma\left( \frac{1}{2}  \right)=\sqrt{ \pi } \implies \Gamma\left( -\frac{1}{2} \right)=-2\sqrt{ \pi }
   $$
   Per $n$ generico troviamo:
$$
	\Gamma\left( -n+\frac{1}{2} \right)=(-1)^n  \frac{2^n\sqrt{ \pi }}{(2n-1)!!}
   $$


**Lezione associata:** [[4.Funzione Gamma di Eulero]]