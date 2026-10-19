
Per prima cosa partiamo dall'equazione di Shrödinger stazionaria nel caso unidimensionale.
$$
	-\frac{\hbar^2}{2m} \frac{d^2}{dt^2}\psi+V(x)\psi=E\psi
$$
Si tratta di un'equazione alle derivate ordinarie che sappiamo risolvere, conviene però fare alcune osservazioni preliminari.

1. Per $E$ fissato e potenziale $V(x)$ generico, la soluzione generata è una combinazione lineare di 2 (poichè l'eq. è di grado 2) soluzioni particolari. 
   $$
   	\psi_{E}=Au_{E}(x)+Bv_{E}(x)
   $$
2. Date due soluzioni per $E$ fissato possiamo andare a definire il Wronksiano: 
$$
   	W_{E}(x)=u'_{E}(x)v_{E}(x)-u_{E}(x)v'_{E}(x)
   $$
   Se $u_{E} \text{ e } v_{E}$ sono soluzioni, allora il wronksiano è costante:
   $$
	\begin{aligned}
	W'_{E}&=u''v+u'v'-uv''-u'v'=u''v+uv''=\\
	&=-\frac{2m}{\hbar^2}(E-V(x))(u_{E}v_{E}-u_{E}v_{E})=0
	\end{aligned}
   $$
3. $W_{E}=0\iff u_{E}\propto v_{E}$, cioè $u_{E}$ e $v_{E}$ sono linearmente dipendenti
4. Per soluzioni normalizzate su $\mathbb{R}$ gli autovalori di $\hat{H}$ sono NON DEGENERI, cioè, dato $E_{n}$ autovalore, i corrispondenti $u_{n} \text{ e } v_{n}$ sono t.c. $u_{n}\propto v_{n}$.
   Infatti $u_{n}$ e $v_{n}$ devono annullarsi all'infinito (per la normalizzazione), dunque all'infinito $W_{n}=0$, ma, poichè $W_{n}(x)=\text{cost}$ ovunque, allora il Wronksiano sarà ovunque nullo e $u_{n}$ e $v_{n}$ saranno proporzionali tra loro.

Facciamo adesso un'osservazione di natura classica. Riscriviamo l'equazione in questa forma:
$$
	\frac{\psi''}{\psi}=\frac{2m}{\hbar^2}(V(x)-E)
$$
Le regioni classicamente permesse sono quelli in cui l'energia $E>V(x)$, allora $\frac{\psi''}{\psi}<0$ e la funzione d'onda sarà oscillante. Nelle regioni classicamente proibite avrò $\frac{\psi''}{\psi}>0$ e la mia funzione d'onda avrà andamento esponenziale.

![[Pasted image 20261013205135.png]]

Vedremo come in meccanica quantistica dovremo andare a studiare anche le regioni classicamente proibite.

5. Preso un potenziale simmetrico $V(x)=V(-x)$, le soluzioni normalizzabili hanno parità definita: 
$$
   	\psi_{n}(x)=\pm \psi_{n}(-x)
   $$
   Infatti se sostituisco $\psi(-x)$ nell'equazione di Shrödinger (stazionaria) ottengo: 
   $$
	-\frac{\hbar^2}{2m} \frac{d^2}{dx^2}\psi(-x)+V(x)\psi(-x)=E\psi(-x)
   $$
   Poichè $V(-x)=V(x)$ anche $\psi(-x)$ è soluzione dell'equazione di Shrödinger.
   Ulteriormente, dalla conservazione del Wronksiano so che le soluzioni normalizzabili sono tra loro linearmente dipendenti: 
   $$
	\begin{cases}
	\psi_{n}(x)=C\psi_{n}(-x) \\
	\psi_{n}(-x)=C\psi_{n}(x)
	\end{cases}\implies C^2=1 \text{ e } C=\pm 1
   $$