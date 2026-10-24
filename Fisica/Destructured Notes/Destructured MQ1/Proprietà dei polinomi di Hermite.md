
**Argomenti utili:** [[Funzioni Generatrici]]

I polinomi di Hermite sono un insieme di polinomi ortogonali in $L^2(-\infty,+\infty)$. 
Di seguito ne elenchiamo alcune proprietà utili.

1. Esiste una funzione generatrice per i polinomi di Hermite.
   Posto $S(z,\xi)\equiv e^{ -z^2+2z\xi }$ si ha che: 
   $$
	S(z,\xi)=\sum^\infty_{n=0} \frac{z^n}{n!}H_{n}(\xi)
   $$
   cioè:$$H_{n}(\xi)=\frac{ \partial^nS }{ \partial z^n }|_{z=0}$$
2. Vale la seguente formula per la derivata: 
$$
   	\begin{aligned}
	\frac{ \partial S }{ \partial \xi }=2zS&\implies \sum^\infty_{n=0} \frac{z^n}{n!}H'_{n}(\xi) =2z\sum^\infty_{n=0} \frac{z^n}{n!}H_{n}(\xi)=\sum_{n=0}^\infty 2 \frac{z^{n+1}}{n!}H_{n}(\xi)\\
	(H'_{0}(\xi)=0)&\implies \sum^\infty_{n=1} \frac{z^n}{n!}H'_{n}(\xi)=2\sum^\infty_{n=1} \frac{z^n}{(n-1)!}H_{n-1}(\xi)\\
	&\implies H'_{n}(\xi)=2nH_{n-1}(\xi)
	\end{aligned}
   $$
3. I polinomi di Hermite sono legati da una relazione di ricorrenza:
$$
	\begin{aligned}
	\frac{ \partial s }{ \partial z }=2(\xi-z)S &\implies \sum_{n=0} \frac{z^{n-1}}{(n-1)!}H_{n}(\xi)=2 \sum_{n=0} \frac{(\xi-z)z^n}{n!}H_{n}(\xi)\\
	&\implies \sum_{n=0} \frac{z^n}{n!}H_{n+1}(\xi)=2\sum_{n=0} \frac{(\xi-z)z^n}{n!}H_{n}(\xi)\\
	&\implies H_{n+1}-2\xi H_{n}(\xi)+2nH_{n-1}(\xi)=0 \quad (n=1,2,\dots)
	\end{aligned}
$$
   Se combiniamo i punti (2) e (3) otteniamo l'equazione differenziale si cui sono soluzione
4. Sono soluzione di una particolare equazione differenziale, detta equazione di Hermite.
   Deriviamo 2 volte la relazione di ricorrenza:
$$
	\begin{aligned}
	H_{n+1}'-2\xi H_{n}'-2H_{n}+2nH_{n-1}'&=0\\
	H_{n+1}''-2\xi H_{n}''-4H'_{n}+2nH_{n-1}''&=0
	\end{aligned}
$$
   A questo punto applichiamo la formula per le derivate:
$$
	\begin{cases}
	H''_{n+1}=(H'_{n+1})'=2(n+1)H'_{n}=4n(n+1)H_{n-1} \\
	H''_{n}=2nH'_{n-1} \\ \\
	H'_{n}=2nH_{n-1}
	\end{cases}
   $$
   Sostituiamo all'interno della relazione di ricorrenza derivata 2 volte:
$$
	4n(n+1)H_{n-1}-\xi 4nH'_{n-1}-8nH_{n-1}+2nH''_{n-1}=0; \quad (n-1=0,1,\dots)
   $$
   Sostituendo $n-1$ con $n$ otteniamo:
$$
	\implies H''_{n}-2\xi H'_{n}+2nH_{n}=0
$$
   Che è esattamente l'equazione che abbiamo risolto, per $\varepsilon-1=n$. Dunque la funzione generatrice $S$ mi genera effettivamente le soluzioni all'equazione differenziale.
5. Per trovare i polinomi di Hermite vale la seguente formula, detta formula di Rodriguez:
$$
\begin{aligned}
H_{n}(\xi)&=\frac{ \partial^n S }{ \partial z^n }|_{z=0}=\frac{ \partial ^n }{ \partial z^n } e^{ -z^2+2z\xi }|_{z=0}\\
&=e^{ \xi^2 }\frac{ \partial ^n }{ \partial z^n } e^{ -(z-\xi)^2 }|_{z=0}=(-1)^n e^{ \xi^2 }\frac{ \partial ^n }{ \partial \xi^n }e^{ -(z-\xi)^2 }|_{z=0}\\
&=(-1)^n e^{ \xi^2 } \frac{d^n}{d\xi^n}e^{ -\xi^2 } 
\end{aligned}   	
   $$
   Da questa formula si ritrovano le condizioni sulla parità di cui parlavamo prima:
$$
	H_{n}(-\xi)=(-1)^n H_{n}(\xi)
   $$

**Lezione Associata:** [[4.Oscillatore armonico quantistico]]