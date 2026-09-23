---
corso: Meccanica statistica
data: 2026-09-17
tags:
  - lezione
argomenti:
  - Termodinamica
lezione-precedente: "[[Termodinamica (lezione 1)]]"
source: Kardar's MIT lessons
---


> [!info] Contesto
> Corso: Meccanica Statistica
> Argomenti previsti: 

## Riassunto veloce

L'obiettivo di questa lezione è andare a definire in maniera esatta il differenziale $\delta Q$ come fatto per il lavoro nel caso di trasformazioni quasi-statiche. Per farlo sfruttiamo il secondo principio della termodinamica e il suo utilizzo nello studio dell'efficienza delle macchine termiche. In particolare sfruttando le macchine di Carnot ed il teorema di Carnot è possibile definire una scala di temperature, la scala termodinamica, indipendente dal sistema/sostanza utilizzato e si può andare a dimostrare come $Q$ sia proporzionale a questa $T$.
In seguito, tramite il teorema di Clausius, definiamo l'entropia per poi andare a riscrivere $\delta Q=TdS$.

## Appunti

### Il secondo principio della Termodinamica

Abbiamo visto che per trasformazioni quasi-statiche è possibile andare a calcolare $\delta W$ come $\delta W=\sum_{i}J_{i}dx_{i}$, vorremmo poter fare lo stesso per $\delta Q$.
Sappiamo che l'equilibrio meccanico viene "quantificato" dalle forze generalizzate $J$, analogamente l'equilibrio termico viene "quantificato" tramite la temperatura $\Theta$. Per quel che riguarda gli spostamenti generalizzati il corrispondente sarà l'entropia $S$ e questo ci porta al secondo principio.

Studiamo il procedimento storico che portò alla formulazione del secondo principio.
Il secondo principio nasce dalla necessità di costruire macchine che potessero trasformare calore in lavoro e dallo studio della loro efficienza.
Definiamo meglio cos'è l'efficienza $\eta$. Studiamo una macchina termica che funziona prendendo una certa quantità di calore $Q_{H}$ da una sorgente di calore, ne trasforma una parte in lavoro $W$ e rilascia il calore rimanente $Q_{C}$ nell'ambiente. Allora l'efficienza della macchina è:
$$
	\eta = \frac{W}{Q_{H}} = \frac{Q_{H}-Q_{C}}{Q_{H}}\leq 1
$$
cioè il rapporto tra il lavoro prodotto e il calore fornito.

Analogamente posso definire una macchina inversa, frigorifera, che riceve lavoro dall'esterno $W$ per assorbire calore $Q_{C}$ da un sistema freddo per cedere calore $Q_{H}$ ad un sistema più caldo. In questo caso non si parla più di efficienza ma si può comunque definire un concetto analogo, la performance:
$$
	\omega = \frac{Q_{C}}{W}=\frac{Q_{C}}{Q_{H}-Q_{C}}
$$
$\omega$ sarà sempre maggiore di 1.
Partendo da questi e andando a definire cosa sia possibile o meno in accordo con il secondo principio, andremo a riscrivere il calore come un differenziale esatto.

Nel farlo useremo 2 formulazioni distinte del secondo principio.
- **Principio di Kelvin**: Nessun processo è possibile il cui solo risultato sia conversione di calore in lavoro ($\eta<1$)
- **Principio di Clausius**: Nessun processo il cui solo risultato sia il trasferimento di calore da un corpo più freddo a uno più caldo è possibile

Queste due formulazioni sono tra loro equivalenti cioè $K \iff C$.
Per farlo basta dimostrare che $\bar{K} \to \bar{C} \quad \& \quad \bar{C}\to \bar{K}$, cioè nel caso in cui uno dei due principi sia violato lo è anche l'altro.

Immagino di avere una macchina che viola il principio di Kelvin e trasforma tutto il calore ricevuto da una sorgente in lavoro. Collego questa macchina a una macchina frigorifera che sfrutta il lavoro fornito dalla macchina "anti-Kelvin" per raffreddare un corpo più freddo e scaladare il corpo caldo che fornisce calore alla macchina "anti-Kelvin". Se considero le due macchina nel loro insieme ottengo una macchina il cui unico risultato è trasferire calore da un corpo freddo a uno più caldo, violando clausius.

Immaginiamo ora di avere una macchina che viola Clausius. Colleghiamo a questa macchina una macchina termica che prende parte del calore generato dalla macchina "anti-Clausius" e ne trasform una parte in lavoro e restituisce parte del calore alla sorgente fredda. Se noi scegliamo la seconda macchina in modo tale da restituire alla sorgente fredda quantità di calore pari a quella assorbita dalla macchina "anti-Clausius" e consideriamo le due macchine nell'insieme, andiamo ad ottenere una macchina il cui solo risultato è trasformare calore in lavoro, violando il principio di Kelvin.

Lo step successivo alla costruzione della funzione entropia è lo studio di una macchina ideale, la macchina di Carnot.

#### Macchine di Carnot e temperatura termodinamica

Definiamo macchina di Carnot qualunque macchona che sia:
1. **Reversibile**, cioè ogni processo può essere invertito semplicemente invertendo input e output (è una "generalizzazione" dei sistemi privi di attrito in meccanica)
2. **Ciclica**, l'inizio e la fine del ciclo termodinamico coincidono
3. Tutti gli scambi di calore avvengono tra due sorgenti (o bagni) a temperature distinte e costanti $T_{H}$ e $T_{C}$, una calda (Hot) e una fredda (Cold).
Studiamo l'esempio della macchina di Carnot per i gas ideali.
![[ciclo-carnot.png]]
i cammini 1-2 e 3-4 giacciono sulle isoterme, i cammini 4-1 e 2-3 sono adiabatici, nel senso in cui non avviene scambio di calore.
Lungo i cammini adiabatici ho che per definizione $\delta Q = 0 = dE-\delta W = dE+pdV$. Dove l'ultima uguaglianza vale nel caso di trasformazioni quasi-statiche.
Dunque: $E(p,V)=E(pV)=\frac{3}{2}pV$ (l'ultima uguaglianza vale nel caso di gas ideali monoatomici).
In questa maniera otteniamo:
$$
	\delta Q = d\left( \frac{3}{2}pV \right)+pdV = \frac{5}{2}pdV+\frac{3}{2}Vdp 
$$
Essendo la trasformazione adiabatica:
$$
	0=\frac{dp}{P} +\frac{5}{3} \frac{dV}{V}=d(\ln(pV^{5/3})) \Rightarrow pV^\gamma = const
$$
con $\gamma=\frac{5}{3}$. In questo modo abbiamo descritto la curva adiabatica nel piano di Clapeyron.

Una proprietà essenziale delle macchine di Carnot è descritta dal seguente teorema:
- **Teorema di Carnot**: Nessuna macchina termica che opera tra due bagni a temperatura $T_{H}$ e $T_{C}$ è più efficiente di una macchina di Carnot.
**Dimostrazione**: Considero una macchina irreversilbile (dunque non una macchina di Carnot) che opera completamente tra $T_{H}$ e $T_{C}$ per generare lavoro. Considero ora una macchina di Carnot che opera tra le stesse sorgenti di calore. Collego la macchina di Carnot, usata come macchina frigorifera, alla macchina non-Carnot. Siano $Q_{H}'$ e $Q_{C}'$ le quantità di calore assorbito e ceduto dalla macchina non-Carnot e $Q_{H}$ e $Q_{C}$ le quantità di calore assorbite dalla macchina di Carnot. Considerando le due macchine nel loro insieme otteniamo una macchina che assorbe $Q'_{H}-Q_{H}$ e cede $Q'_{C}-Q_{C}$. Per il principio di Clausius il calore può venire trasferito solo dalla sorgente calda a quella fredda, pertanto il calore ssorbito dev'essere positivo e $Q_{H}'\geq Q_{H}$. Poichè il lavoro coinvolto nel processo è lo stesso, allora:
$$
	\eta_{Carnot} = \frac{W}{Q_{H}}\geq \frac{W}{Q_{H}'}=\eta_{non-Carnot}
$$
Un ulteriore conseguenza di ciò è che tutte le macchine di Carnot che operano tra le 2 stesse temperature hanno la stessa efficienza. Allora l'efficienza di una macchina di Carnot, indipendentemente da come l'ho costruita e da come opera, dev'essere un funzione di $T_{H}$ e $T_{C}$, $\eta=\eta(T_{H},T_{C})$.

Questa proprietà ci permette di definire una scala di temperatura in maniera universale, indipendentemente dalle proprietà dei gas ideali. Definiamo questa scala la *Scala Termodinamica delle Temperature*.

**Costruiamo questa scala:**
Considero due macchine di Carnot in serie. La prima che opera tra $T_{1}$ e $T_{2}$, producendo lavoro $W_{12}$ e la seconda che opera tra $T_{2}$ e $T_{3}$ e produce un lavoro $W_{23}$.
Considerando le 2 macchine insieme, ciò che otteniamo è una macchina di Carnot equivalente che opera tra $T_{1}$ e $T_{3}$ e produce un lavoro $W_{13}=W_{12}+W_{23}$.
![[Temp_Termo.png]]
Studiamo gli scambi di calore di queste macchine.
$$
	\begin{aligned}
	Q_{2} &= Q_{1}-W_{12}=Q_{1}[1-\eta(T_{1},T_{2})] \\
	Q_{3} &= Q_{2}-W_{23}=Q_{2}[1-\eta(T_{2},T_{3})]=Q_{1}[1-\eta(T_{1},T_{2})][1-\eta(T_{2},T_{3})]\\
	Q_{3} &= Q_{1}-W{13}=Q_{1}[1-\eta(T_{1},T_{3})]
	\end{aligned}
$$
Dunque:
$$
	1-\eta(T_{1},T_{3})=(1-\eta(T_{2},T_{3}))(1-\eta(T_{1},T_{2}))
$$
e $$1-\eta(T_{1},T_{2})=\frac{Q_{2}}{Q_{1}}\left( \frac{Q_{3}}{Q_{3}} \right)=\frac{1-\eta(T_{2},T_{3})}{1-\eta(T_{1},T_{3})}=\frac{f(T_{2})}{f(T_{1})}$$
dove $f(T)$ è una funzione qualsiasi. Per convenzione prendiamo:
$$
	1-\eta(T_{1},T_{2})=\frac{T_{2}}{T_{1}} \quad \Rightarrow \quad \eta(T_{H},T_{C})=\frac{T_{H}-T_{C}}{T_{H}}
$$
Così ho ottenuto il rapporto di proporzionalità tra 2 temperature, allora ho bisogno di scegliere anche un punto di riferimento, come il punto triplo dell'acqua, $T_{triplo}=273.16°K$.
Ovviamente questa scala non è molto utile da un punto di vista pratico ma ha un vantaggio concettuale, cioè la possibilità di andare a definire una scala di temperature indipendente dalla sostanza utilizzata. La temperature è per definizione positiva, infatti se esistesse una temperatura negativa, poichè $\frac{Q_{2}}{Q_{1}}=\frac{T_{2}}{T_{1}}$ , otterei che una macchina di Carnot che opera tra 2 bagni di cui uno a temperatura positiva e uno a temperatura negativa assorbe calore da entrambe le sorgenti e le converte in lavoro, violando Kelvin.

### Entropia

Riprendiamo la domanda iniziale. Siamo riusciti in qualche modo a legare il calore alla temperatura, ma ci manca ancora il corrispettivo degli "spostamenti generalizzati".
Per costruire questa nuova funzione di stato (partendo dal secondo principio) facciamo uso del seguente teorema:
- **Teorema di Clausius**
## Domande per revisione
- [ ] 

## Collegamenti
- Lezione precedente: [[Termodinamica (lezione 1)]]
- Concetti collegati: [[]]

