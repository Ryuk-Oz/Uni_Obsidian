
Occupiamoci dello studio dell'equazione completa, in 3 dimensioni ed in presenza di un potenziale.
$$
	\psi(x,t)\to \psi(\vec{r},t)
$$
Sulla derivata temporale non cambia nulla, la derivata spaziale invece, imponendo l'isotropia dello spazio (cioè l'invarianza per rotazione), diventa l'operatore Laplaciano.
$$
	\frac{ \partial^2 \psi }{ \partial x^2 } \to \Delta \psi
$$
Nel caso in cui andassimo a considerare $n$ particelle, semplicemente andremmo a riscrivere il laplaciano per uno spazio $3n$ dimensionale.
Dunque l'equazione per la particella libera di 3 dimensioni è:
$$
	i\hbar \frac{ \partial \psi }{ \partial t } =-\frac{\hbar^2}{2m}\Delta \psi
$$
Cosa succede se introduciamo un potenziale scalare $V=V(\vec{r},t)$?
Ricordiamo il modo in cui possiamo riscrivere l'equazione (per particella libera) tramite operatori:
$$
	i\hbar \frac{ \partial  }{ \partial t }=\hat{E}; \quad -\frac{\hbar^2}{2m}\Delta=\hat{K}  
$$
Ricordiamo inoltre che nello "spazio delle $x$" gli operatori posizione e impulso sono:
$$
	\hat{p}=-i\hbar \frac{ \partial  }{ \partial x }; \quad \hat{x}=x\cdot
$$
A questo punto andiamo a studiare l'energia TOTALE in presenza di un potenziale.
$$
	E\to H=\frac{|\vec{p}|^2}{2m}+V(\vec{r},t)
$$
...ma... $\frac{|\vec{p}|^2}{2m}=K$, che sottoforma di operatore diventa $-\frac{\hbar^2}{2m}\Delta$.
Devo "operatoricizzare" $V(\vec{r},t)$. La prima strategia (nonchè la più intuitiva e al contempo quella vincente) è di implementare $V$ come un operatore moltiplicativo, analogamente ad $\hat{x}$.
Con queste considerazioni possiamo riscrivere l'equazione di Shrödinger $3$-d in presenza di potenziale.

>[!Summary] Equazione di Shrödinger
>
>$$
>	i\hbar \frac{ \partial \psi }{ \partial t } =-\frac{\hbar^2}{2m}\Delta \psi+V(\vec{r},t)\psi
>$$

A questo punto non ci resta che verificare che quest'equazione sia compatibile con le interpretazioni di natura fisica.
Per prima cosa verifichiamo la compatibilità con l'interpretazione fisica.
Come sappiamo, $\psi(\vec{r},t)$ dev'essere un'ampiezza di probabilità di posizione, pertanto il seguente integrale ci deve restituire la probabilità di trovare la particella in un certo volume $V$.
$$
	P(V,t)\equiv \int_{V} d^3x \, \rho(x,t) \qquad \rho(\vec{r},t)=|\psi(\vec{r},t)|^2
$$
Nel caso in cui stia studiando più di una particella e volessi sapere qual è la probabilità di trovare la prima in $V_{1}$ e la seconda in $V_{2}$ ecc..., andrei semplicemente ad utilizzare l'ampiezza di probabilità congiunta, la quale è funzione di tutte le coordinate e di tutte le particelle.
$$
	P(V_{1},V_{2},\dots;t)=\int_{V_{1}} d^3r_{1}\dots \int_{V_{n}}d^3r_{n}\,|\psi(\vec{r}_{1},\vec{r}_{2},\dots;t)|^2
$$
Nel caso mi interessasse trovare la posizione di $n-1$ particelle indipendentemente dalla posizione della prima particella, mi basta utilizzare la probabilità marginale, andrei cioè ad integrare la particella 1 su tutto lo spazio.
Anche questa probabilità congiunta dev'essere normalizzata a $1$.

##### Conservazione della probabilità

Appurato cosa intendiamo con "interpretazione probabilistica" ora che siamo passati alle 3 dimensioni, andiamo ad imporre la normalizzazione.
$$
	\int_{V_{TOT}} d^3x \, |\psi(\vec{r},t)|=1
$$
A questo punto vogliamo che una volta imposta la normalizzazione in un dato istante, per comodità prendiamo $t=0$, la funzione resti normalizzata anche al variare di $t$.

Studiamo dunque la probabilità $P$ al variare del tempo.
Inizio dallo studio di $\rho$ al variare del tempo.
$$
	\begin{aligned}
	\frac{ \partial  }{ \partial t } \rho(\vec{r},t)=\frac{ \partial  }{ \partial t } |\psi(\vec{r},t)|^2=\psi^*\frac{ \partial \psi }{ \partial t } +\frac{ \partial \psi^* }{ \partial t } \psi
	\end{aligned}
$$
Studiamo i vari termini separatamente.
$$
	\begin{aligned}
	\frac{ \partial \psi }{ \partial t } &=-\frac{i}{\hbar}\left( -\frac{\hbar^2}{2m}\Delta \psi +V\psi \right)\\
	\frac{ \partial \psi^* }{ \partial t } &=\frac{i}{\hbar}\left( -\frac{\hbar^2}{2m} \Delta \psi^*+V\psi^*\right)\psi \\
	\implies \frac{ \partial \rho }{ \partial t } &=-\frac{i}{\hbar} \psi^*\left( -\frac{\hbar^2}{2m}\Delta \psi\dots \right)+\frac{i}{\hbar} \psi\left( -\frac{\hbar^2}{2m}\Delta \psi^*\dots \right)=\\
	&=\frac{i}{\hbar} \frac{\hbar^2}{2m}(\psi^*\Delta \psi-\Delta \psi^*\psi)=\\
	&=-\vec{\nabla } \cdot\left[ -\frac{i\hbar}{2m}(\psi^*\vec{\nabla}\psi-\psi  \vec{\nabla}\psi^* ) \right]
	\end{aligned}
$$
A questo punto possiamo definire una nuova quantità $\vec{J}(\vec{r},t)$, densità di corrente di probabilità, nel seguente modo:
$$
	\begin{aligned}
	\vec{J}(\vec{r},t)&\equiv-\frac{i\hbar}{2m}(\psi^*\vec{\nabla}\psi-\psi  \vec{\nabla}\psi^* )=-\frac{i\hbar}{2m}(\psi^* \vec{\nabla}\psi-(\psi^* \vec{\nabla}\psi)^*)=\\
	&=-\frac{i\hbar}{2m}2i\mathrm{Re}(\psi^* \vec{\nabla}\psi)=\mathrm{Re}\left[ \frac{i\hbar}{m}\psi^* \vec{\nabla \psi} \right] \in \mathbb{R}
	\end{aligned}
$$
Dunque la densitò di corrente di probabilità è reale e $\rho$ è compatibile conm un'equazione di continuità senza sorgenti o pozzi:
$$
	\frac{ \partial \rho }{ \partial t }+\vec{\nabla}\cdot \vec{J}=0 
$$
Pertanto la probabilità $P(V,t)$ non può essere nè creata nè distrutta ma può fluire liberamente tra un volume e l'altro ed è globalmente conservata sul laboratorio.
$$
	\frac{ \partial P }{ \partial t }=\int_{V} d^3x\, \frac{ \partial \rho }{ \partial t }=-\int_{\partial V} \vec{J}\cdot \vec{n} \, dS   
$$
Andando a studiare la variazione di $P$ su tutto il laboratorio, troviamo che essendo $\vec{J}$ quadratico nella funzione d'onda ed essendo la funzione d'onda normalizzabile, lavoriamo di default con condizione al contorno di annullamento al bordo, indipendentemente che il lab sia finito o infinito. Pertando: $\frac{ \partial  }{ \partial t }P_{TOT}=0$.

##### Conseguenze della linearità dell'equazione

Come ben sappiamo, la linearità è "la formalizzazione matematica del principio di sovrapposizione".
$$
	\text{se } \psi_{i}(\vec{r},t) \text{ sono soluzioni per } i=1,2,\dots n \\
	\implies \sum_{i}\alpha_{i}\psi_{i}(\vec{r},t) \quad (\alpha_{i}\in \mathbb{C}) \quad \text{è ancora soluzione}
$$
Dunque le soluzioni dell'edS formano uno spazio vettoriale in $\mathbb{C}$. Ulteriormente sappiamo che le funzioni devono essere normalizzabili e lo spazio risulta essere normato (dotato di prodotto scalare con norma positiva).
Tale spazio funzionale è lo spazio $L^2(V)$ che spesso approssimeremo a $L^2(\mathbb{R})$.
Questo in meccanica classica non succede mai perchè molto spesso lavoriamo con equazioni non lineari su varità complesse (basti pensare al pendolo semplice). Dunque sotto certi aspetti in meccanica quantistica lavoriamo in uno spazio più comodo, ma vi è un prezzo da pagare. Lo spazio $L^2$ è uno spazio funzionale e in quanto tale ha dimensione infinita che a volte può causare problemi. (In meccanica classica lavoriamo con $2n$ variabili; $n$ posizioni ed $n$ momenti).

Andiamo dunque a definire il prodotto scalare in $L^2$.
$$
	\begin{aligned}
	\forall \psi_{1},\psi_{2} &\in L^2\\
	(\psi_{1},\psi_{2}) &\equiv \int d^3r\,\psi_{1}^*(\vec{r},t)\,\psi_{2}(\vec{r},t)
	\end{aligned}
$$
Sfruttando questo possiamo definire la norma $\forall \psi \in L^2$:
$$
	(\psi,\psi)=||\psi||=\int d^3r \, |\psi(\vec{r},t)|^2=1
$$
Ricordandoci che noi andiamo sempre a misurare $|\psi|^2$ otteniamo che stati definiti a meno di una costante moltiplicativa (che poi vado a normalizzare) o di una fase (che si riassorbe col modulo), vanno a definire lo stesso "stato fisico" che misuriamo.
$$
		\psi\sim C\psi e^{ i\theta }
$$
Cioè gli stati fisici corrispondono a dei raggi in $L^2$.

Questo spazio $L^2$ in cui stiamo lavorando è uno spazio di Hilbert $(\mathcal{H})$ COMPLETO e SEPARABILE, ma affronteremo questo argomento più avanti con calma.

**OSSERVAZIONE:** i vettori di $\mathcal{H}$ sono in corrispondenza biunivoca con le condizioni iniziali $\psi(\vec{r},0)$, poi l'equazione mi da come queste condizioni evolvono nel tempo MA non mi fornisce dei nuovi vettori dello spazio.

##### Evoluzione temporale dei valori medi

Come ultima verifica della compatibilità fisica andiamo a studiare come evolvono nel tempo i valori medi di osservabili fisiche. L'intuito ci dice che queste osservabili debbano evolvere seguendo leggi classiche.
Studiamo funzioni di $\vec{r}$, di $\vec{p}$ e di entrambi insieme.
$$
	\begin{aligned}
	<f(\vec{r})>&\equiv \int_{V} d^3r \, \psi^*\,f(\vec{r}) \, \psi=\int_{V} d^3r \, f(\vec{r})|\psi(\vec{r},t)|^2\\
	<g(\vec{p})> &\equiv \int_{V}d^3r\, \psi^*\,g(\hat{p})\,\psi=\int_{V}d^3r\,\psi^* \, g(-i\hbar \vec{\nabla})\,\psi\\
	<F(\vec{r},\vec{p})> & \equiv \int_{V}d^3r\,\psi^* \, F(\vec{r}, -i\hbar \vec{\nabla})\,\psi
	\end{aligned}
$$
A questo punto è bene fare un'osservazione sul caso di dipendenza da entrambi.
Se la funzione dipendesse dal prodotto tra i 2, otterei: $F(xp_{x})\neq F(p_{x}x)$ perchè l'operatore $\hat{p}$ non è commutativo!.
$$
	(\hat{x}\hat{p}_{x}-\hat{p}_{x}\hat{x})\psi=[\hat{x},\hat{p}_{x}]\psi=\left( -i\hbar x \frac{ \partial \psi }{ \partial x } +i\hbar x\frac{ \partial \psi }{ \partial x } +i\hbar \psi \right)=i\hbar \psi(x)
$$
cioè: $[\hat{x},\hat{p}]=i\hbar \mathbb{1}$
Occupiamoci ora dello studio di alcuni valori medi nello spacifico:
$$
	\begin{aligned}
	\frac{d}{dt}<x>_{\psi,t} &= \frac{d}{dt}\int d^3r \,\psi^*x\,\psi = \int d^3r \,\psi^*x \frac{d\psi}{dt}+\int d^3r \frac{\,d\psi^*}{dt}x\psi\\
	&=\frac{i\hbar}{2m}\int d^3r \,(\psi^*x\,\Delta \psi-\Delta \psi^*x\,\psi) \quad\text{(stesso passaggio del calcolo di } \vec{J}\text{)}\\
	&=\frac{i\hbar}{2m}\int d^3r \,(\psi^*x\,\Delta \psi+ \vec{\nabla}\psi^* \cdot \vec{\nabla}(x\psi)-\vec{\nabla}\cdot(\vec{\nabla}(\psi^*)x\psi)\\
	&=\frac{i\hbar}{2m}\int d^3r \,(\psi^*x\,\Delta \psi+\vec{\nabla}\psi^* \cdot \vec{\nabla}(x\psi))-\frac{i\hbar}{2m}\int_{\partial V}ds\, \vec{\nabla}(\psi^*)x\psi\cdot \vec{n}\\
	&=\frac{i\hbar}{2m}\int d^3r \,(\psi^*x\,\Delta \psi+\vec{\nabla}\psi^* \cdot \vec{\nabla}(x\psi)) \quad \text{(l'ultimo termine si è annullato sul bordo)}\\
	&=\frac{i\hbar}{2m}\int d^3r\,(\psi^*x\,\Delta \psi+ \vec{\nabla}\cdot(\psi^*\vec{\nabla}(x\psi))-\psi^*\Delta(x\psi))\\
	&=\frac{i\hbar}{2m}\int d^3r\, (\psi^*x\,\Delta \psi-\psi^*\Delta(x\psi)) \quad \text{(come prima un termine si annulla al bordo)}
	\end{aligned}
$$
studiamo $\Delta (x\psi)$, faccio su una solo variabile, poi generalizzo:
$$
	\begin{aligned}
	\frac{ \partial^2 (x\psi) }{ \partial x^2 }&=\frac{ \partial  }{ \partial x } \frac{ \partial (x\psi) }{ \partial x }=\frac{ \partial  }{ \partial x }\left( \psi+x\frac{ \partial \psi }{ \partial x }  \right)   \\
	&=2 \frac{ \partial \psi }{ \partial x } +x\frac{ \partial^2 \psi }{ \partial x^2 } 
	\end{aligned}
$$
Dunque:
$$
	\begin{aligned}
	\frac{d}{dt}<x>_{\psi,t}&=\frac{i\hbar}{2m}\int d^3x\,\left( \psi^*x\Delta \psi-2\psi^*\frac{ \partial \psi }{ \partial x } -\psi^*x \Delta \psi \right)\\
	&=-\frac{i\hbar}{m}\int d^3x\, \psi^* \frac{\partial\psi}{\partial x}=\frac{1}{m}\int d^3x\,\psi^*\left( -{i\hbar}\frac{ \partial  }{ \partial x }   \right)\psi = \frac{<p_{x}>_{\psi,t}}{m}= <v>_{\psi,t}
	\end{aligned}
$$
è ho ritrovato la relazione classica $p=mv$.

Proviamo a fare lo stesso con la derivata del momento.
$$
	\begin{aligned}
	\frac{d}{dt}<p_{x}>_{\psi,t}&\equiv \frac{d}{dt}\int d^3x\,\psi^*\left( -i\hbar \frac{ \partial  }{ \partial x } \psi \right)\\
	&=-i\hbar\int d^3x\, \frac{d}{dt}\left( \psi^*\frac{ \partial \psi }{ \partial x } \right) = -i\hbar\int d^3x\, \frac{\partial\psi^*}{\partial t}\frac{ \partial \psi }{ \partial x } +\psi^* \frac{ \partial  }{ \partial x } \frac{ \partial \psi }{ \partial t }  \\
	&=\int d^3x\,\left( -\frac{\hbar^2}{2m}\Delta \psi^*+V\psi^* \right)\frac{ \partial \psi }{ \partial x } -\psi^* \frac{ \partial  }{ \partial x } \left( -\frac{\hbar^2}{2m}\Delta \psi +V\psi\right) \\
	&=-\int d^3x\,\psi^*\frac{ \partial (V\psi) }{ \partial x } -V\psi^*\frac{ \partial \psi }{ \partial x } \quad \text{come prima elimino i laplaciani integrando per parti}\\
	&=-\int d^3x\,\psi^*\frac{ \partial V }{ \partial x } \psi =-<\frac{ \partial V }{ \partial x } >_{\psi,t}= <F_{x}>_{\psi,t}
	\end{aligned}
$$
Anche in questo caso vado a ritrovare le leggi classiche.
Eleviamo questi risultati a postulati e diciamo che i valori medi delle osservabili fisiche evolvono nel tempo secondo leggi classiche. (Teorema di Ehrenfest).