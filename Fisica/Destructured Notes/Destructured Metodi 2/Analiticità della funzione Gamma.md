
Occupiamoci dello studio dell'analiticità della funzione $\Gamma$.
Partiamo da quello che è il dominio di esistenza della funzione. Abbiamo definito $\Gamma$ attraverso un integrale che converge per ogni valore di $z$ tale che $\mathrm{Re}(z)>0$. Dunque la funzione $\Gamma$ è definita solo nel semipiano positivo.

![[Pasted image 20261020225846.png]]

In questo semipiano la funzione è analitica?
Per studiare l'analiticità utilizziamo il fatto che una funzione è analitica $\iff$ è derivabile
Dobbiamo dunque calcolare:
$$
	\frac{d\Gamma}{dz}=\frac{d}{dz}\int_{0}^\infty e^{ -t }t^{z-1}dt
$$
A questo punto entra in gioco un teorema utile, il teorema della convergenza dominata, che ci dice che se l'argomento dell'integrale è maggiorato in tutti gli intervalli da qualcosa che NON dipende da $z$, allora posso derivare sotto il segno di integrale. Verifichiamo che le ipotesi del teorema siano soddisfatte.
$$
	\begin{aligned}
	\text{prendo } &\delta>0,\quad M<\infty,\quad\text{t.c.} \quad\delta<\mathrm{Re}(z)<1\\
	\implies &|e^{ -t }t^{z-1}|<e^{ -t }t^{\delta-1} \quad \text{per }0<t<1\\
	\text{e} \quad &1<\mathrm{Re}(z)<M\\
	\implies &|e^{ -t }t^{z-1}|<e^{ -t }t^{M-1}\quad \text{per } 1<t<\infty
	\end{aligned}
$$
L'argomento è maggiorato efficacemente in tutti gli intervalli, allora posso derivare sotto il segno di integrale.
$$
	\frac{d\Gamma}{dz}=\int^\infty_{0} \frac{e^{ -t }}{t} \frac{d}{dz}(t^z)dt
$$
Ricordiamo che $t^z$ è una funzione polidroma, pertanto dobbiamo starci attenti:
$$
	\frac{d}{dz}t^z=\frac{d}{dz}\{ e^{z\log t} \}=\log (t) e^{ z\log t }=t^z \log(t)
$$
Dunque:
$$
	\frac{d\Gamma}{dz}=\int^\infty_{0} e^{ -t }t^{z-1} \log t \, dt
$$
Che continua a convergere nel semipiano positivo $\implies \Gamma(z)$ è analitica (quindi nom ha singolarità nel semipiano reale). Essendo analitica mi aspetto di poter trovare una continuazione analitica nel semipiano negativo.

**Lezione associata:** [[4.Funzione Gamma di Eulero]]