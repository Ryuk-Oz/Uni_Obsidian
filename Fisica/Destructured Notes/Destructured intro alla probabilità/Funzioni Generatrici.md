
Forniamo un po' di formalismo utile allo studio di molti campi della probabilità.

Consideriamo una variabile aleatoria $x$ che assume valori interi $0,1,\dots k$ con probabilità $P_{0},P_{1},\dots P_{k}$, la funzione generatrice $G(s)$ di $x$ è definita nel seguente modo.
$$
	G(s)\equiv \sum^\infty_{k=0}s^kP_{k}
$$
riprendendo la definizione di valore medio: 
$$
	E(F(k))\equiv \sum^\infty_{k=0}F(k)P_{k}
$$
Possiamo concludere che $G(s)=E(s^k)$.

Uteriormente avendo definito $G(s)$ tramite una somma di probabilità è evidente che $G(1)=1$ per le proprietà di normalizzazione.
Per le proprietà delle potenze otteniamo invece $G(0)=P_{0}$.
Possiamo anche sfruttare la funzione generatrice per inferire la probabilità di ogni evento.
$$
	\begin{aligned}
	G'(0)&=\frac{dG}{ds}|_{s=0}=\sum ks^{k-1}P_{k}{|_{s=0}}=P_{1}\\
	\implies P_{n}&=\frac{1}{n!} \frac{d^nG}{ds^n}|_{s=0}
	\end{aligned}
$$

Infine osserviamo che $G'(1)=\sum_{k}kP_{k}= <k> =E(k)$

Proviamo ora a considerare $x_{1},x_{2},x_{2},\dots,x_{n}$, $n$ variabili aleatorie **indipendenti** con funzioni generatrici $G_{1}(s),G_{2}(s),\dots,G_{n}(s)$. Allora possiamo calcolare la funzione generatrice di $y=x_{1}+x_{2}+\dots x_{n}$ come:
$$
	G_{y}(S)=\prod^n_{i=1}G_{i}(s)
$$
Il risultato si dimostra per $n=2$ e poi si procede per induzione.