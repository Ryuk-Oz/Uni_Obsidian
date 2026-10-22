
**Utile da rivedere:** [[Continuazione analitica]]

Cerchiamo un modo di continuare analiticamente la funzione Gamma e studiare che comportamento assume al di fuori del semipiano positivo.
Ci aspettiamo che ci siano dei problemi in $\mathrm{Re}(z)=0$. Negli altri punti invece?

Il primo modo per estendere analiticamente è la ricorrenza fattoriale.
Consideriamo la funzione $\Gamma(z+1)$ definita e analitica per $\mathrm{Re}(z)>-1$ (quindi è definita al di fuori del dominio di esistenza e analiticità di $\Gamma(z)$).
$$
	\Gamma(z+1)=\int^\infty_{0} e^{ -t }t^z dt
$$
Integro questo integrale per parti:
$$
	=-e^{ -t }t^z|^{^\infty}_{_{0}}+z\int^\infty_{0} e^{ -t } t^{z-1}dt
$$
La soluzione scritta in questa forma è ben definita solo per $\mathrm{Re}(z)>0$. Al di fuori di questa regione il nuovo integrale non converge (ed il primo termine anche non converge).
Però  se $\mathrm{Re}(z)>0$ trovo:
$$
	\Gamma(z+1)=z\Gamma(z)
$$
Dunque: 
$$
	\Gamma(z)=\frac{\Gamma(z+1)}{z} ,\qquad \mathrm{Re}(z)>0
$$
Poichè $\Gamma(z)$ e $\frac{\Gamma(z+1)}{z}$ hanno infiniti punti di accumulazione in un intersezione dei propri domini di analiticità (l'intero semipiano positivo), allora posso usare $\frac{\Gamma(z+1)}{z}$ per estendere analiticamente $\Gamma(z)$ sulla striscia $-1<\mathrm{Re}(z)\leq 0$.
Da questa nuova rappresentazione notiamo subito coem la funzione Gamma abbia un polo semplice in $z=0$, con residuo pari a 1 (il rsiduo è semplicemente $\Gamma(1)$).
In modo totalmente analogo posso continuare a continuare $\Gamma(z)$ per striscie, trovando un polo semplice ad ogni intero negativo.
$$
	\Gamma(z)= \frac{\Gamma(z+n)}{z(z+1)(z+2)\dots(z+n-1)}
$$
I poli si trovano in $z=-n,\, n\in \mathbb{N}$ con $\text{Res}= \frac{(-1)^n}{n!}$.

![[Pasted image 20261020233244.png]]


**Lezione associata:** [[4.Funzione Gamma di Eulero]]