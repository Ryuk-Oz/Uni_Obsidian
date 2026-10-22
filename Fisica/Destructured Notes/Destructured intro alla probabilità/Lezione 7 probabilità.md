
## Persistenza e transienza del random walk

Un random walk è persistente se torna sicuramente in $\vec{x}=0$
Se $d\leq {2}$ il random walk è persistente.
Se $d\geq 3$ il random walk è transiente, cioè c'è una probabilità non nulla di non tornare nell'origine.

Occupiamoci dello studio della persistenza del random walk.

Definisco:
$u(t)\equiv \text{prob che il RW sia in } x=0 \text{ al tempo }t$
$f(t)\equiv \text{probabilità che il RW sia in }x=0\text{ al tempo }t \text{ per la prima volta}$
Dunque possiamo riscrivere $u(t)$ facendo uso di $f(t)$.
$$
	u(t)=f(t)+f(t-1)u(1)+f(t-2)u(2)+\dots+ f(1)u(t-1) \qquad (1)
$$
Da qua concludiamo il risultato (ovvio) che $u(t)\geq f(t)$.
Condizioni iniziali:
- $u(0)=1$ (a $t=0$ mi trovo in $x=0$)
Per risolvere questo problema posso fare uso delle funzioni generatrici/caratteristiche:
$$
	F(s)=\sum_{t=0}^\infty s^t f(t), \quad U(s)=\sum_{t=0}^\infty s^t u(t)
$$
Sostituisco nell'equazione (1).
$$
\begin{aligned}
\sum^\infty_{t=1} s^tu(t)&=\sum^\infty_{t=1}s^t f(t)u(0)+\sum^\infty_{t=1}s^tf(t-1)u(1)+\dots \sum^\infty_{t=1}s^tf(1)u(t-1)+\left( \sum s^t f(0)u(t) \right)=\\ 
	&=\sum_{t=1}^\infty s^t\sum_{k=0}^{t-\not{1}} f(t-u)u(k)
\end{aligned}	
$$
Passando alla somma $t=0$ devo aggiungere un termine pari a 0:
$$
	\sum_{t=1}^\infty s^t u(t)=\sum^\infty_{t=0}s^tu(t)-u(0)=U(s)-1
$$
$$
	\sum_{t=0}^\infty s^t\sum_{k=0}^{t} f(t-k)u(k)=F(s)U(s)=U(s)-1 \qquad  (2)
$$
E i 2 uno si elidono a vicenda.
Dimostro l'equazione $(2)$:
$$
	\begin{aligned}
	F(s)U(s)&=\sum^\infty_{p=0}s^p f(p ) \sum^\infty_{q=0}s^qu(q)=\sum^\infty_{p}\sum^\infty_{q}s^{p+q}f(p)u(q)=\sum_{n=0}^\infty s^n \sum_{q=0}^\infty u(q)f(n-q)\\
	\text{quando } q>n &\implies n-q<0, \text{ poichè } f(k)=0\, \forall k\leq 0 \text{ allora ritrovo la forma che volevo dimostrare:}\\
	F(s)U(s)&=\sum_{n=0}^\infty s^n \sum_{q=0}^n u(q) f(n-q)
	\end{aligned}
$$

Definiamo bene la persistenza:
$$
	\text{persistenza} \iff f\equiv \sum_{t=0}^\infty f(t)=1
$$
Posso riscriverlo anche come:
$$
	f=\lim_{ s \to 1 } F(s)=1
$$
Riprendendo i risultati di prima ottengo che:
$$
	U(s)=\frac{1}{1-F(s)}
$$
Posso allora riformulare la persistenza come:
$$
	\lim_{ s \to 1 } U(s)\to +\infty
$$
Cioè se il random walk è persistente ritorno infinite volte nell'origine.

Quest'ultima condizione è "facile" da verificare

Consideriamo il limite in cui $t\gg 1$
$$
	u(t)\simeq p_{t}(0)
$$
dove:
$$
	p_{t}(x)=\frac{1}{\sqrt{ 2\pi t }}e^{ -x^2/(2t) } \quad (d=1)
$$
$$
	U(1)=\lim_{ T \to \infty } \sum^T_{t=0} u(t) \simeq \lim_{ T \to \infty } \int_{0}^T \frac{1}{\sqrt{ 2\pi t }}dt=\lim_{ T \to \infty } \frac{2}{\sqrt{ 2\pi }}T^{1/2}=\infty
$$
Estendendo il problema a dimensioni superiori vado semplicemente a considerare una gaussiana in $d$ dimensioni.
$$
	p_{t}(x)=\frac{1}{(2\pi t)^{d/2}}e^{ -|\vec{x}|^2/(2t) } \qquad \vec{x}=\text{vettore } d \text{ dimensionale}
$$
Ma a noi interessa solo il fattore di normalizzazione.
$$
	U(1)=\lim_{ T \to \infty } \int^T_{0} \left( \frac{1}{2\pi t} \right)^{d/2}\simeq \lim_{ T \to \infty } \int_{0}^T \frac{dt}{t^{d/2}} = \begin{cases}
	T^{1/2}\to \infty \quad d=1 \\
	\ln T\to \infty \quad d=2 \\
	\frac{1}{T^{1/2}}<\infty \quad  d=3
	\end{cases}
$$
Dunque per $d\geq3$ il random walk non è persistente.

In particolare in $d=3$ ho:
$$
	U(1)\simeq {1},51\dots\implies f=0.34
$$


## Catene di Markov

Si tratta di un modo per studiare procesis stocastici discreti
Iniziamo definendo:
$$
	p_{i}(t)=P[X_{t}=i] \quad i\in \mathbb{Z}, t\in \mathbb{N}
$$
Probabilità di trovare la variabile $X$ in un certo sito $i$ al tempo $t$.
Questa probabilità dipende dalla posizione della variabile nel tempo precedente, si tratta dunque di una probabilità condizionata (basta pensare al modello del random walk in una dimensione).
$$
	P[X_{t+1}=j|X_{t}=i_{1} \cap X_{t-1}=i_{2}\cap\dots\cap X_{t-s}=i_{s}]
$$
Se questa probabilità dipende solo dalla posizione immediatamente precedente, allora parliamo allora di processo Markoviano o senza memoria:
$$
	P[x_{t+1}=j|X_{t}=i]
$$
Un processo markoniano equivale a un'equazione differenziale in ambito deterministico.
Un processo non markoviano corrisponde invece ad un'equazione integrale.

Per studiare processi di questo tipo è fondamentale introdurre una Matrice di Transizione:
$$
	W_{ij}(t)=P[X_{t+1}=j|X_{t}=i]
$$
La scelta di tenere lo stato di partenza come primo indice e lo stato di arrivo come secondo indice è puramente convenzionale.
Questa matrice soddisfa alcune proprietà:
1. $W_{ij}(t)\geq 0$
2. $\sum_{j}W_{ij}=1$ (somma sul secondo indice, sto dicendo che partendo da uno stato $i$ la somma delle probabilità di spostarsi su ciascuno stato raggiungibile fa 1).
Matrici che soddisfano queste due proprità prendono il nome di matrici stocastiche.
Convenzionalmente mettiamo il primo indice sulle colonne e il secondo indice sulle righe.
L'evoluzione della catena di Markov è data da:
$$p_{j}(t+1)=\sum_{i}p_{i}(t)W_{ij}(t)$$

## Processi stazionari

Ci occupiamo principalmente di processi stazionari, cioè processi per i quali $W_{ij}$ non dipende dal tempo.
$$
	\sum_{j}p_{j}(t+1)=1=\sum_{j}\sum_{i}p_{i}(t)W_{ij}=\sum_{i}p_{i}(t)\sum_{j}W_{ij}=\sum_{i}p_{i}(t)=1
$$
Dunque la seconda condizione sulla matrice serve a preservare la normalizzazione.

Esempio: RW simmetrico in 1D
Modellando il RW con una catena di Markov devo identificare la matrice di transizione:
$$
	W_{i,i+1}=W_{i+1,i}=\frac{1}{2} \qquad \text{e} \qquad W_{i,j}=0 \quad\text{ negli altri casi}
$$
Dunque troviamo:
$$\begin{aligned}
p_{i}(0)&=\delta_{i 0}\\
p_{j}(1)&=\sum_{i}p_{i}(0)W_{ij} = p_{0}(0)W_{0j}=\begin{cases}
\frac{1}{2} \quad j=-1 \\
\frac{1}{2} \quad j=1
\end{cases}
\end{aligned}
$$
NOTA BENE: In reltà l'importante per processi Markoviani è che la memoria sia finita, non necessariamente 1.
Per farlo consideriamo l'esempio di un processo che abbia memoria dei 2 processi precedenti.
$$
	P[X_{t+1}=j | X_{t}=i \cap X_{t-1}=j]
$$
A questo punto aumento la dimensione dello spazio degli eventi e considero una nuova probabilità:
$$
	P[X_{t},Y_{t}\equiv X_{t-1}|X_{t-2}]
$$
E mi sono ricondotto al caso di prima (?).

## Distribuzione stazionaria

Parliamo di distribuzione stazionaria se esiste:
$$
	\lim_{ t \to \infty } p_{i}(t)\equiv \pi_{i}
$$
Cioè da un certo punto in poi $p_{i}$ smette di dipendere dal tempo.
E vale:
$$
	\pi_{j}=\sum_{i}\pi_{i}\cdot W_{ij}
$$
**Oss:** Non è detto che esista la distribuzione stazionaria $\pi$. Ad esempio nel random walk non esiste una distribuzione stazionaria.

**Esempio semplice**: Catena di Markov a 2 stati.
Catena in cui la variabile aleatoria può assumere solo 2 valori $X=\{ 0,1 \}$, tipo il lancio di una moneta (ma il lancio di una moneta non è una catena di Markov).
Consideriamo il processo in cui $X$ cambia stato con probabilità $p$ e resta nello stesso stato con probabilità $1-p$.
Possiamo modellare il processo come un grafo:
![[Pasted image 20261020120454.png|526]]
scriviamo la matrice di transizione:
$$W=
	\begin{pmatrix}
	1-p & p \\
	p & 1-p
	\end{pmatrix}
$$
Cerchiamo la distribuzione stazionaria.
Intuitivamente ci viene da pensare che $\vec{\pi}=\left( \frac{1}{2}, \frac{1}{2} \right)$.
Sappiamo che $\vec{\pi}=\vec{\pi}\cdot W$ dunque:
$$
	(\pi_{0},\pi_{1})=(\pi_{0},\pi_{1})\begin{pmatrix}
	1-p & p \\
	p & 1-p
	\end{pmatrix}
$$
E otteniamo:
$$
	\begin{cases}
	\pi_{0}=(1-p)\pi_{0}+p\pi_{1} \\
	\pi_{1}=p\pi_{0}+(1-p)\pi_{1} \\
	\pi_{0}+\pi_{1}=1 \quad \text{ per la normalizzazione}
	\end{cases}
$$
Risolvendo il sistema troviamo:
$$
	\begin{cases}
	\pi_{0}=\pi_{1} \\
	\pi_{0}+\pi_{1}=1
	\end{cases}
$$
E torniamo al risultato atteso.

Occupiamoci di studiare l'evoluzione della catena partendo da condizioni iniziali generiche:
$$
	\vec{p}(0)=(p_{0},1-p_{0})=(p_{0}(0),p_{1}(0))
$$
$p_{0}=$ probabilità di trovarsi nello stato 0 all'istante iniziale.
Studiamo l'evoluzione partendo da questa condizione iniziale mediante la matrice di transizione.
$$
	(p_{0}(1),p_{1}(1))=(p_{0}(0),p_{1}(0))\begin{pmatrix}
	1-p & p \\
	p & 1-p & 
	\end{pmatrix}
$$
Guardiamo cosa troviamo al tempo $t+1$.
$$
	\begin{cases}
	p_{0}(1)=(1-p)p_{0}(0)+p\,p_{1}(0) \\
	p_{0}(2)=(1-p)p_{0}(1)+p\,p_{1}(1) \\
	\dots \\
	p_{0}(t+1)=(1-p)p_{0}(t)+p\,p_{1}(t)
	\end{cases}
$$
L'altra equazione è: $p_{1}(t+1)=p\,p_{0}(t)+(1-p)p_{1}(t)$
Mettendo queste due a sistema e sfruttando la normalizzazione $p_{1}+p_{0}=1$ otteniamo:
$$
\begin{aligned}
	p_{0}(t+1)&=p+(1-2p)p_{0}(t)=p+(1-2p)[p+(1-2p)p_{0}(t-1)]=\\
	&=p+p(1-2p)+(1-2p)^2p_{0}(t-1)=\dots=\\
	&=p[1+(1-2p)+(1-2p)^2+\dots]+(1-2p)^{t+1}p_{0}(0)=\\
	&=p\sum^t_{k=0} (1-2p)^k + (1-p)^{t+1}p_{0}(0)=\\
	&=p \frac{1-(1-2p)^{t+1}}{1-(1-2p)}+(1-2p)^{t+1}p_{0}(0)\\
	&=\frac{1}{2}-\frac{1}{2}(1-2p)^{t+1}+(1-2p)^{t+1}p_{0}(0)\\
\implies p_{0}(t)&=\frac{1}{2}+(1-2p)^t\left[ p_{0}-\frac{1}{2} \right]
\end{aligned}
$$
Abbiamo che $0<p<1$ (escludo gli uguali altrimenti ottengo un processo deterministico), pertanto $|1-2p|<1$ e va a $0$ per $t\to \infty$.
Dunque abbiamo:
$$
	\lim_{ t \to \infty } p_{0}(t)=\frac{1}{2}=\pi_{0}
$$
Indipendentemente dalle mie condizioni iniziali.

Risultato notevole: se $\vec{p}(0)=\vec{\pi}$ allora trovo che $\vec{p}(t)=\vec{p}(0)=\vec{\pi}$
