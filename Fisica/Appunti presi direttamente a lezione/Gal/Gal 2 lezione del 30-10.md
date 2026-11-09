
In questa sezione ci occupiamo dello studio di strutture di fibrato.

>[!Abstract] **Fibrato Tangente**
>Chiamiamo fibrato tangente il seguente spazio: 
>$$
>	TM=\underset{p\in M}{\cup} T_{p}M
>$$

Mentre le varietà differenziali sono oggetti molto belli con proprietà precise (e localmente uguali a $\mathbb{R}^n$), la struttura di fibrato sembra apparentemente un'accozzaglia di oggetti senza interazioni tra loro.
In realtà fibrato tangente è un insieme con una topologia naturale e una struttura di varietà differenziabile. Il nostro obiettivo è per il momento quello di evidenziare questa struttura.

Prendiamo l'atlante di $M$, cioè:
$$
	\text{Atlante di } M= \{ (U_{i})\subseteq \mathbb{R}^n,\; V_{i}\subseteq M,\; \varphi_{i}:U_{i}\to V_{i} \}
$$
Le mappe $\varphi_{i}$ sono diffeomorfismi su $M$. La terna data da un $U_{i}$, un $V_{i}$ e una $\varphi_{i}$ ci da una carta su $M$. Un insieme di tutte le carte (tale che i $V_{i}$ ricoprano $M$) viene chiamato Atlante.

Sfruttiamo l'atlante per costruire delle **carte su $TM$**:
$$
	U_{i} \times \mathbb{R}^n \overset{\Phi_{i}}{\longrightarrow} TV_{i}
$$
$$
	\Phi_{i}(x,v):=d\varphi_{i}|_{x}(D_{v}) \in T_{\varphi_{i}(x)}V_{i}
$$
Con $v$ intendiamo le derivate direzionali $D_{v}$.
$d\varphi_{i}$ è il differenziale delle carte su $M$. Posso vedere $\varphi_{i}$ come una mappa $C^\infty$ tra varietà:
$$\varphi_{i}:M_{1}=U_{1}\to M_{2}=V_{i}$$
Dunque $d\varphi_{i}|_{x}$ è una mappa tra spazi tangenti:
$$
	d\varphi_{i}|_{x}: T_{x}M_{1}\to T_{\varphi_{i}(x)}M_{2}
$$
A questo punto dobbiamo capire com'è fatto lo spazio tangente di $U_{i}\subseteq\mathbb{R}^n$, $T_{x}M_{1}$:
$$
	T_{x}M_{1}=T_{x}U_{i}=\mathbb{R}^n
$$
Abbiamo così precisato il significato di $d\varphi_{i}|_{x} (D_{v})$. Mappe che prendono vettori tangenti a un punto $x$ su un sottospazio di $\mathbb{R}^n$ che abbiamo chiamato $U_{i}$ e li mandano in vettori tangenti a un sottoinsieme di una varietà differenziabile $M$, che chiamiamo $V_{i}$.
**Osservazione:** prendo sempre una coppia di oggetti, un punto $x$ su cui è "montato" uno spazio tangente, e un vettore tangente $v$ nello spazio tangente. A questi associo rispettivamente un punto $p\equiv\varphi_{i}(x)$ su $M$ sul quale è "montato" $T_{p}M$ e un vettore tangente a $M$, il quale appartiene a $T_{p}M$.

Dunque:
$$
	\mathrm{Im}\Phi_{i}=\underset{p\in V_{i}}{\cup} T_{p}M
$$
A questo punto possiamo dare una forma alle carte su $TM$.
Le carte su $TM$ hanno forma:
$$
	(U_{i}\times \mathbb{R}^n, TV_{i}, \Phi_{i})
$$
In particolare, data una varietà di dimensione $n$, $\text{dim}(TM)=2n$.

Nel caso unidimensionale (la mia varietà M è una curva), posso immaginare un fibrato tangente come qualcosa di questo tipo:

![[Pasted image 20261103212212.png|350]]

In cui i segmenti verticali rappresentano gli spazi tangenti montati su ogni punto (le fibre del fibrato).

La struttura di fibrato tangente è essenziale per poter definire il concetto di campo vettoriale (vettori che in ogni punto variano in modo $C^\infty$).

### Campi vettoriali

>[!abstract] Campo vettoriale
>Un campo vettoriale su $M$ è una mappa $C^\infty$: 
>$$
>	X:M\to TM, \; p\to X_{p}\in T_{p}M
>$$

I campi vettoriali servono a descrivere campi di forze, flussi di liquidi ecc...
Un modo alternativo per vedere un campo vettoriale è vederlo come una sezione del fibrato.

![[Pasted image 20261103212927.png]]

Volendo posso vederlo anche come una sottovarietà in $TM$.

A cosa servono operativamente i campi vettoriali?
I campi vettoriali ci servono per costruire le funzioni derivate:
$$
	f:M\to \mathbb{R}; \quad p\in M; \quad X\in T_{p}M \to X(f(p))\in \mathbb{R}
$$
Preso invece il campo $X$ e ripetuto il processo per ogni punto otteniamo:
$$
	X(f) \; \text{è una nuova funzione} = \text{derivata direzionale di } f \text{ nella direzione di } X \text{ nei vari punti}
$$
Spesso in analisi ci troviamo ad operare con derivate seconde, dunque ci serve un nuovo campo vettoriale $Y$ e la derivata seconda sarà $Y(X(f))$.
Una regola importante (teorema di Schwartz) è che le derivate seconde (in analisi) commutano, cioè
$$\frac{ \partial^2 f }{ \partial x_{i} \partial x_{j} }=\frac{ \partial^2 f }{ \partial x_{j} \partial x_{i} }$$
Questo ci permette di fare alcune importanti osservazioni sulle derivate seconde fatte tramite campi vettoriali. vediamolo da un esempio:
Prendo come varietà $M=\mathbb{R}^n$ e considero due campi, $X=X(x)=\sum a_{i}(x)c_{i}=\sum a_{i}(x)\frac{ \partial  }{ \partial x_{i} }$ 
il vettore geometrico $c_{i}$ è uguale a $\frac{ \partial  }{ \partial x_{i} }$. Il secondo campo è $Y=Y(x)=\sum b_{j}(x)\frac{ \partial  }{ \partial x_{j} }$. Allora:
$$
	\begin{aligned}
	X(Y(f))&=X\left( \sum_{j}b_{j} \frac{ \partial f }{ \partial x_{j} }  \right)=\sum_{i}a_{i} \frac{ \partial  }{ \partial x_{i} } \sum_{j}b_{j} \frac{ \partial f }{ \partial x_{j} }\\ 
	&\sum_{i,j} a_{i} \frac{ \partial b_{j} }{ \partial x_{i} } \frac{ \partial f }{ \partial x_{j} } ++\sum_{i,j} a_{i}b_i \frac{ \partial^2 f }{ \partial x_{i} \partial x_{j} } \\
	Y(X(f)) &=\sum_{i,j} b_{j} \frac{ \partial a_{i} }{ \partial x_{j} } \frac{ \partial f }{ \partial x_{i} } ++\sum_{i,j} a_{i}b_i \frac{ \partial^2 f }{ \partial x_{i} \partial x_{j} } 
	\end{aligned}
$$
Da quei deduciamo che in generale $X(Y)\neq Y(X)$ e $X(Y)=Y(X)$ solo se i campi sono costanti, detto in maniera più formale, di solito i campi vettoriali non commutano, cioè il commutatore è diverso da $0$:
$$
	[X,Y]=X(Y(f))-Y(X(f))\neq0
$$
Dunque $\mathcal{X}(M)=$ insieme di tutti i campi vettoriali su $M$ è dotato di un algebra molto ricca, complementata ulteriormente dall'operatore di commutazione:
- $(X+Y)_{p}=X_{p}+Y_{p}$
- $(\lambda X)_{p}=\lambda X_{p}$
- $(fX)_{p}=f(p)X_{p}$
- $[X,Y]$ che cos'è?
Introduciamo il seguente Lemma:
	il commutatore tra 2 campi, $[X,Y]$ è un nuovo campo vettoriale, ossia una derivazione in ogni punto. Questo non è ovvio perchè il commutatore contiene derivate seconde, ma queste si cancellano e resta solo la derivata prima (vedi esempio di prima).
Dimostriamo formalmente che $[X,Y]$ è una derivazione. La verifica della linearità è ovvia, cosa possiamo dire invece per la regola di Leibniz?
$$
	\begin{aligned}
	[X,Y](fg)&=X(Y(fg))-Y(X(fg))=X(fY(g)+gY(f))-Y(fX(g)+gX(f))=\\
	&=\cancel {X(f)Y(g)}+fX(Y(g))+ \cancel{X(g)Y(f)}+gX(Y(f))\\
	&\cancel{-Y(f)X(g)}-fY(X(g))\cancel{-Y(g)X(f)}-gY(X(f))=\\
	&=fX(Y(g))+gX(Y(f))-fY(X(g))-gY(X(f))=\\
	&=f[X,Y](g)+g[X,Y](f)\quad \blacksquare
	\end{aligned}
$$
Concludiamo che $\mathcal{X}(M)$ è uno spazio vettoriale dotato di un'operazione extra che è bilineare interna ($\mathcal{X}\times \mathcal{X}\to\mathcal{X}$), dotata di 3 proprietà:
- è bilineare
- è anticommutativa: $[X,Y]=-[Y,X]$
- Vale l'identità di Jacobi: $[[X,Y],Z]+[[Z,X],Y]+[[Y,Z],X]=0$
Per questi motivi si $\mathcal{X}$ è un'algebra di lie, come vedremo più avanti

### Flussi

Abbiamo $M$ varietà differenziale e $X$ campo vettoriale. Scegliamo $p \in M$.
Il flusso di $X$ a partire da $p$ è una curva in $M$ $\varphi_{t}$:
$$
	\varphi_{t}(p): (-\varepsilon,\varepsilon)\to M \; \text{t.c.} \; \frac{d}{dt} \varphi_{t}(p)=\dot{\varphi}(t)=X|_{\varphi_{t}(p)}\,,\quad \varphi_{0}(p)=p
 $$
 Si tratta di "una curva che segue l'andamento del campo vettoriale".
 Andiamo a ripetere questo procedimento $\forall p$.
 In questo modo otteniamo una mappa:
 $$
	(-\varepsilon,\varepsilon)\times M\to M, \quad (t,p)\to \varphi_{t}(p)
 $$
 In realtà bisogna fare più attenzione di così, il tempo di esistenza del flusso potrebbe dipendere da $p$.  Per esempio, se $M$ è un segmento e $X=e_{1}$ è il campo vettoriale costante, man mano che $p$ si avvicina agli estremi la soluzione esiste solo per tempi sempre più corti.
 I campi vettoriali più interessanti sono quelli tali per cui il flusso associato $\exists \, \forall t\in \mathbb{R}$ a partire da qualunque punto. Campi di questo tipo si dicono campi completi.

La teoria generale delle eq. differenziali ordinarie implica che se $M$ è una varietà compatta, allora ogni campo vettoriale $X\in \mathcal{X(M)}$ è completo.

Digressione sui ricci $\to$ la sfera non ammette campi vettoriali ovunque costanti.
 
