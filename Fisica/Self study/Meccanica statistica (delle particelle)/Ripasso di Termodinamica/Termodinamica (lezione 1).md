---
corso: Meccanica Statistica
data: 2026-08-25
tags:
  - lezione
argomenti:
  - Termodinamica
lezione-precedente:
source: Kardar's MIT lessons
---


> [!info] Contesto
> Corso: Meccanica Statistica
> Argomenti previsti: 

## Riassunto veloce



## Appunti

### Introduzione

Non è possibile descrivere proprietà termiche e calore a partire dalla meccanica newtoniana, pertanto è necessario un nuovo framework, di natura fenomenologica.

La **Termodinamica** è una descrizione **fenomenologica** delle proprietà legate all'equilibrio di sistemi macroscopici.

Partiremo dall'osservazione di sistemi semplici:
* sistemi isolati da pareti adiabatiche (cioè non avviene scambio di calore)
per poi osservare sistemi più complessi
* sistemi che permettono il passaggio di equilibrio (pareti diatermiche)
Ulteriormente, ci interessa particolarmente l'equilibrio del sistema.
Diciamo che un sistema si trova un equilibrio "rispetto ad una certa proprietà" se questa non varia nel tempo.
Esistono diversi tipi di proprietà interessanti, di natura meccanica, termica ecc... in particolare ci interessa lo studio della seconda categoria di proprietà.

Come abbiamo chiarito da subito, la termodinamica è una materia fenomenologica, cioè studiamo queste proprietà a partire da osservazioni di natura empirica. Con questo procedimento, la prima cosa che incontriamo è il:

>[!abstract] Principio 0 della termodinamica
>Se il sistema A si trova in equilibrio col sistema B e il sistema B si trova in equilibrio col sistema C allora A si trova in equilibrio con C (proprietà di transitività)

In particolare si osserva che se A e B si trovano in equilibrio termico con C, cioè A e C e B e C condividono la stessa temperatura allora A e B condividono a loro volta la stessa temperatura.
Il concetto stesso di temperatura è in realtà una misura empirica nata per descrivere l'equilibrio termico.

>[!note] Dimostrazione del principio 0
>Considero A, B e C descritti da un certo numero di coordinate, $A=A(A_{1},A_{2},\dots)$, $B=B(B_{1},B_{2},\dots)$ e $C=C(C_{1},C_{2},\dots)$.
>L'equilibrio tra A e B implica l'esistenza di un vincolo che lega le coordinate dei due sistemi, descrivibile tramite un'equazione di vincolo:
>$f_{AB}(A_{1},A_{2},\dots,B_{1},B_{2},\dots)=0$
>Analogamente posso descrivere l'equilibrio tra B e C come: 
>$f_{BC}(B_{1},B_{2},\dots,C_{1},C_{2},\dots)=0$
>A questo punto posso manipolare queste relazioni per riscrivere una delle coordinate in funzione delle altre (questo è rigoroso da un punto di vista fisico, fenomenologico, ma non da un punto di vista matematico)
>$B_{1}=F_{AB}(A_{1},A_{2},\dots,B_{2},\dots)$
>$B_{1}=F_{BC}(B_{2},\dots,C_{1},C_{2},\dots)$
>Unendo l'equilibrio tra A e B e quello tra B e C otteniamo:
>$F_{AB}(A_{1},A_{2},\dots,B_{2},\dots)=F_{BC}(B_{2},\dots,C_{1},C_{2},\dots)$
>Questo mi permette di scrivere una nuova equazione di vincolo:
>$f_{AC}(A_{1},A_{2},\dots,C_{1},C_{2},\dots)=0$, dove le coordinate di B diventano variabili in eccesso

Questa dimostrazione, seppuro non particolarmente rigorosa, ci permette di intuire un concetto molto utile. Posso descrivere lo stato di equilibro termico di un sistema tramite una funzione delle loro coordinate, ad esempio $\theta_{A}(A_{1},A_{2},\dots)$, ed equilibrare due sistemi consiste semplicemente nell'uguagliare le 2 funzioni corrispondenti di 2 sistemi diversi.

A questo punto ci interessa riuscire a descrivere efficacemente queste funzioni e le proprietà che vi associamo, come la temperatura. Queste funzioni prendono il nome di coordinate termodinamiche o funzioni di stato. Tutte le curve descritte dall'equazione $\theta_{A}(A_{1},A_{2},\dots)=\theta=\text{cost}$ si dicono curve isoterme.
Tuttavia, per poter definire efficacemente le isoterme, dobbiamo prima assegnare un valore numerico alla Temperatura.

### Scala dei Gas Ideali

Per poter assegnare un valore alla  temperatura è bisogno di un sistema di riferimento. Il sistema in questione è quello dei gas ideali, di particolare importanza nell'ambito della Termodinamica.
Osservazioni empiriche ci mostrano che il prodotto tra pressione e volume di un gas rarefatto a sufficienza è costante lungo le sue isoterme. Il termine **gas ideale** si riferisce a gas reali rarefatti e la temperatura di gas ideale è proporzionale a questo prodotto tra pressione e volume. La costante di proporzionalità è determinata prendendo come riferimento il punto triplo dell'acqua ed è fissato a 273.16 gradi Kelvin. Usando come termometro un gas ideale (rareffatto dunque $P\to 0$), la temperatura del sistema si può ottenere da:
$$
	T(°K)\equiv 273.16 \times (\lim_{ P \to 0 } (PV)_{\text{sistema}}/\lim_{ P \to 0 } (PV)_{\text{punto triplo } H_{2}O} )
$$
### Primo principio della Termodinamica

Sempre continuando con l'approccio fenomenologico, occupiamoci adesso delle trasformazioni tra diversi stati di equilibrio.
Queste trasformazioni sono reggiungibili applicando *calore* o *lavoro* al sistema. Il primo principio afferma che sia calore che lavoro siano forme di *energia* e che l'energia totale si conserva.
Partiamo da questa affermazione:
* *La quantità di lavoro necessaria a cambiare lo stato di un sistema isolato adiabaticamente dipende solo dallo stato finale e da quello iniziale e non dai mezzi attraverso i quali si compie il lavoro, nè dagli stati intermedi attraverso cui il sistema passa*
Come conseguenza possiamo concludere l'esistenza di una nuova funzione di stato, l'energia $E(\mathbf{X})$. A meno di una costante, $E(\mathbf{X})$ può essere ottenuta dalla quantità di lavoro $\Delta W$ necessaria per una trasformazione adiabatica dallo stato iniziale $\mathbf{X_{i}}$ a uno finale $\mathbf{X_{f}}$.
$$
	\Delta W=E(\mathbf{X_{f}})-E(\mathbf{X_{i}})
$$
Per trasformazioni generiche, non adiabatiche, il lavoro compiuto non equivale alla differenza di energia interna. La differenza $\Delta Q=\Delta E-\Delta W$ è definita come il calore guadagnato dal sistema dall'ambiente esterno. Ovviamente in trasformazoni di questo tipo lavoro e calore non sono separatamente funzioni di stato (lo sono solo quando poi li unisco in $E$).
Nel caso di trasformazioni infinitesime possiamo scrivere:
$$
	\delta Q=dE-\delta W
$$
dove possiamo riscrivere il differenziale della funzione come $dE=\sum_{i}\partial_{i}E\,dX_{i}$, mentre lo stesso non si può dire per $\delta Q$ e $\delta W$.
(Attenzione! La convenzione dei segni indica come positiva l'energia acquisita dal sistema).

Una trasformazione quasi-statica è una trasformazione che avviene così lentamente da lasciare il sistema sempre in equilibrio. In questo caso, ad ogni stage del processo, le coordinate esistono e sono teoricamente calcolabili. Per trasformazioni di questo tipo, il lavoro compiuto sul sistema (così come quello compiuto dal sistema) può essere legato a variazioni di queste coordinate.
Solitamente il procedimento per fare ciò consiste nel dividere le funzioni di stato $\{\mathbf{X}\}$ in un set di *spostamenti generalizzati* $\{\mathbf{x}\}$ con le  *forze generalizzate* $\{J_{i}\}$ a loro associate, così che per una trasformazione quasi statica infinitesima si possa scrivere:
$$
	\delta W = \sum_{i} J_{i} \,dx_{i}
$$
(solitamente gli spostamenti sono grandezze estensive e le forze grandezze intensive).
Alcuni esempi per sistemi termodinamici possono essere la tensione (forza) e la lunghezza (spostamento) in un filo, la pressione (forza) e il volume(spostamento) in un fluido, il campo elettrico(forza) e la polarizzazione(spostamento) in un materiale dielettrico ecc...
In particolare per gas ideali conviene prendere come coordinate:
$(V, -p)$, con la pressione presa negativamente.

*Esperimento di Joule sull'espansione libera di un gas ideale*
Le osservazioni sperimentali ci mostrano che nei gas ideali, se un gas si espande adiabaticamente (ma non per forza in modo quasi statico) da un volume $V_{i}$ a uno $V_{f}$, la temperatura iniziale e finale resta invariata. Visto che la trasformazione è adiabatica ($\Delta Q=0$) e non viene compiuto lavoro esterno sul sistema ($\Delta W = 0$), allora l'energia interna del gas resta invariata.
Poichè il volume varia ma la temperatura no, deduciamo che l'energia interna dipenda solo dalla temperatura: $E(V,T)=E(T)$. (Questo ritornerà quando vedremo le equazioni di stato del gas perfetto).

Introduciamo ora un ulteriore concetto. Le *funzioni di risposta* sono il metodo utilizzato solitamente per caratterizzare i comportamenti macroscopici di un sistema. Vengono misurate sperimentalmente dalla variazione delle coordinate Termodinamiche di un sistema sottoposto ad input esterni. Alcune funzioni di risposta comuni sono:
- **Capacità Termica**, ottenuta dalla variazione di temperatura quando aggiungo calore al sistema. Per un Gas possiamo calcolare il calore specifico a volume o pressione costante, $C_{V} = \delta Q / dT|_{V}$ e $C_{P} = \delta Q / dT|_{P}$ .
$$
	C_{V} = \frac{dE-\delta W}{dT}|_{V} = \frac{dE}{dT}|_{V}+\frac{PdV}{dT}|_{V} = \frac{ \partial E }{ \partial T }|_{V} 
$$
$$
	C_{P} = \frac{ \partial E }{ \partial T } |_{P}+P \frac{ \partial V }{ \partial T } |_{P}
$$
- **Costanti di Forza**, misure del rapporto infinitesimo tra spostamento e forza, e sono generalizzazioni della costante elastica. Ad esempio la suscettività magnetica (isoterma) $\chi_{T}=\frac{ \partial M }{ \partial B }|_{T}$ o la compressibilità di un gas (isoterma).
- **Risposte Termiche**, misure della variazione di coordinate termodinamiche al variare della temperatura, ad esempio l'espansività di un gas $\alpha_{P}=\frac{ \partial V }{ \partial T }|_{P}$  che per gas perfetti equivale a $\frac{1}{T}$.

## Domande per revisione
- [ ] Qual è lo scopo della termodinamica?
- [ ] Qual è il principio zero della termodinamica? E il primo principio?
- [ ] Come posso quantificare la Temperatura per mezzo di Gas Ideali?
- [ ] Definisci funzioni di Stato e funzioni di risposta

## Collegamenti
- Lezione precedente: [[]]
- Concetti collegati: [[]]

