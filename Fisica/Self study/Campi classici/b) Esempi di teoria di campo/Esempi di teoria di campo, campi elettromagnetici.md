---
corso: Teoria dei campi classica
data: 2026-08-16
tags:
  - lezione
argomenti:
  - Campi_classici
lezione-precedente: "[[Quantità conservate in teorie di campo]]"
---


> [!info] Contesto
> Corso: Teoria dei campi classica
> Argomenti previsti:  Formulazione covariante dell'elettromagnetismo, come le equazioni di Maxwell emergono da un principio variazionale a partire da una certa Lagrangiana di campo

## Riassunto veloce

Partendo dall'equazione del moto di una particella immersa in un campo elettromagnetico abbiamo riscritto le equazioni di Maxwell in forma covariante tramite il tensore di campo $F^{\mu \nu}$. A questo punto abbiamo mostrato come metà delle equazioni di Maxwell siano automaticamente soddisfatte quando andiamo a definire il tensore di campo come il differenziale di un quadripotenziale $A^\mu$, invariante sotto trasformazioni di Gauge.
Infine scrivendo la lagrangiana del quadripotenziali abbiamo visto come le restanti equazioni di Maxwell emergano da un principio variazionale.

## Appunti

L'esempio primario di teoria di campo e quella dell'elettromagnetismo che su scale microscopiche diventa elettrodinamica quantistica, alla base della QFT. Esistono ovviamente altri esempi nei quali questo formalismo si rivela particolarmente utile come la gravità, la meccanica dei fluidi e la meccanica dei corpi elastici. Tuttavia, per semplicità questi ultimi verranno aggiunti piano piano nel futuro, a causa anche di una ridotta utilità rispetto agli esami che devo preparare in questo periodo.

### Campi e potenziali

Partiamo da quello che ci è già noto della teoria elettromagnetica, per poi riscrivere il tutto in forma covariante e sfruttare quanto discusso nelle sezioni precedenti.
Il campo magnetico $B(x)$ e quello elettrico $E(x)$ sono normalmente definiti scrivendo le equazioni del moto di un punto materiale di carica $q$ soggetta ai campi, tramite l'equazione della forza di Lorentz:
$$
	\frac{d\mathbf{P}}{dt}=q\mathbf{E}+q\mathbf{v}\times \mathbf{B}
$$
Moltiplicando per $dt$ otteniamo:
$$
	dP^i = qE_{i}dt+q\epsilon_{ijk}dx^jB_{k}
$$
nell'arco di $dt$ la variazione di energia della particella è $dP^0=(d\mathbf{P}/dt)\cdot d\mathbf{x}$.
Cioè 
$$
	dP^0=qE_{i}dx^i
$$
Possiamo combinare le due equazioni così trovate in un'equazione singola:
$$
	dP^\mu=qF^{\mu \nu}dx_{\nu}
$$
dove abbiamo definito $F^{\mu \nu}$ nel seguente modo (abbiamo usato la convenzione per cui c=1):
$$
	F^{\mu \nu}=\begin{pmatrix} 
	0 & E_{1} & E_{2} & E_{3} \\
	-E_{1} & 0 & B_{3} & -B_{2} \\
	-E_{2} & -B_{3} & 0 & b_{1}  \\
	-E_{3} & B_{2} & -B_{1} & 0
	\end{pmatrix}
$$
Vien da se come $F^{\mu \nu}$ debba essere un tensore (prende un covettore e mi restituisce un vettore).
Le equazioni del moto per $F^{\mu \nu}$ nella loro forma moderna (cioè le equazioni di Maxwell) sono:
$$
	\begin{aligned}
	\partial_{\nu}\epsilon^{\mu \nu \rho \sigma}F_{\rho \sigma}&=0,\\
	\partial_{\nu}F^{\mu \nu}&=\mathcal{J}^\mu.
	\end{aligned}
$$
dove $\mathcal{J}^\mu$ è la corrente elettrica: la componente 0-esima è la densità di carica mentre i termini j-esimi rappresentano la densità di corrente.
Molto spesso è utile e necessario introdurre un quadripotenziale $A^\mu(x)$ tale che:
$$
	F_{\mu \nu} = \partial_{\mu}A_{\nu}-\partial_{\nu}A_{\mu}
$$
In questa forma l'equazione $\partial_{\nu}\epsilon^{\mu \nu \rho \sigma}F_{\rho \sigma}=0$ è automaticamente soddisfatta. ($F_{\rho \sigma}$ è una forma esatta, cioè $dA=F$ e $dF=0$, il tensore di campo è definito come il differenziale del quadripotenziale. Questo è ulteriormente sottolineato dalla natura antisimmetrica di $F$ ).
Se considero un quadripotenziale $\overline{A}^\mu$ legato ad $A^\mu$ tramite l'aggiunta del gradiente di un campo scalare:
$$
	\overline{A}^\mu(x)=A^\mu(x)+\partial^\mu \Lambda(x),
$$
allora i due quadripotenziali portano allo stesso campo. Una trasformazione di questo tipo prende il nome di trasformazione di Gauge.

### Lagrangiana di campo elettromagnetica

Dopo aver riformulato le equazioni di Maxwell in forma covariante, vediamo ora come si possa riscrivere la teoria partendo da un principio variazionale e da una lagrangiana di densità.
Consideriamo la seguente lagrangiana:
$$
	\mathfrak{L} = -\frac{1}{4}F_{\mu \nu}F^{\mu \nu}+\mathcal{J_{\mu}}A^\mu
$$
consideriamo $A^\mu$ come il campo di cui studiare le variazioni e $F_{\mu \nu}$ come un modo veloce di scrivere di differenziale di $A$.
Deriviamo ora le equazioni di Eulero-Lagrange:
$$
	\frac{ \partial \mathfrak{L} }{ \partial (\partial_{\nu}A_{\mu}) } =F^{\mu \nu},\quad \frac{ \partial \mathfrak{L} }{ \partial A_{\mu} } = \mathcal{J}^\mu 
$$
Dunque le equazioni di Eulero-Lagrange per il campo elettromagnetico sono:
$$
	\partial_{\nu}F^{\mu \nu} = \mathcal{J}^\mu
$$
Che soddisfano la parte delle equazioni di Maxwell che non viene automaticamente soddisfatta dalla definizione di $F_{\mu \nu}$.


## Domande aperte / cose da rivedere
- [x] Rivedi da fisica 3 come le equazioni di maxwell così scritte equivalgano alle equazioni di maxwell "standard"

## Collegamenti
- Lezione precedente: [[Quantità conservate in teorie di campo]]
- Concetti collegati: [[Formulazione di una teoria di campo (classica) col formalismo lagrangiano]]

