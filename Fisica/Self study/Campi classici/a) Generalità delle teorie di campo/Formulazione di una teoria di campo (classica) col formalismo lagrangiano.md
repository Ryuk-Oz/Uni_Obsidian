---
corso: Teoria dei campi classica
data: 2026-07-30
tags:
  - lagrangiane
  - studio_individuale
argomenti:
  - Campi_classici
lezione-precedente:
---


> [!info] Contesto
> Corso: Teoria dei campi classica
> Argomenti previsti: Formulazione lagrangiana di una teoria di campo, equazioni del moto e sorgenti di campo

## Riassunto veloce

Come fatto con per la meccanica del punto materiale, è possibile formulare le teorie di campo come quella elettromagnetica attraverso un formalismo di tipo lagrangiano. Per farlo si introduce una nuova funzione $\mathfrak{L}$ detta lagrangiana di densità che dipende anche dai campi coinvolti nel fenomeno che ci interessa descrivere. In modo totalmente analogo a quanto affrontato nei corsi di meccanica analitica, è possibile ricavare le equazioni del moto tramite il principio di azione stazionaria, ottenendo un sistema di equazioni in tutto e per tutto analogo ad Eulero-Lagrange

## Appunti

### Costruzione della teoria

L'obiettivo è quello di costruire una teoria che ci permetta di studiare la variazione di campi di diverso tipo: campi tensoriali $F_{\mu\nu}(t,x)$ e campi scalari $\rho(t,x)$. Per farlo introduciamo un formalismo lagrangiano, analogo a quello sviluppato per la meccanica di punti materiali che ci permetta di trovare come variano i campi nello spazio e nel tempo al posto della legge oraria di ogni punto materiale coinvolto.
Per avere una notazione uniforme diamo un nuovo nome ad ogni componente: $\phi_{1}=\rho$, $\phi_{2 }=F_{01}$, ecc...
Come abbiamo fatto nello studio della meccanica classica, per formulare una teoria di campo, definiamo una funzione scalare $\mathfrak{L}$ che dipenda da ogni componente dei campi e dalle loro derivate (derivate superiori alla prima si usano poco in fisica).
$$
\mathfrak{L} = \mathfrak{L}(\phi_{k},\partial_{\mu }\phi_{k}, \partial_{\mu}\partial_{\nu}\phi_{k, \dots}, x,t)
$$
A questo punto andiamo a definire l'azione non più come un integrale temporale ma come un integrale spazio-temporale.
$$
A = \int d^4x \mathfrak{L}(\phi_{k},\partial_{\mu}\phi_{k}\dots, x,t)
$$
$\mathfrak{L}$ viene detta Lagrangiana di densità della teoria, in quanto $L=\int d^3x\mathfrak{L}$
Ad ogni teoria di campo viene associata una diversa lagrangiana di densità.
Introduciamo ora un esempio di teoria di campo che descrive la variazione di un singolo campo scalare $\phi$ , a questo esempio non è associato alcun sistema fisico reale ma resta comunque un esempio utile alla comprensione del formalismo e viene ampiamente usato in QFT.
$$
	\mathfrak{L} = -\frac{1}{2}(\partial_{\mu}\phi)(\partial^\mu \phi)-\frac{m^2}{2}\phi^2
$$
Un'osservazione preliminare che possiamo fare su questa lagrangiana è che è una funzione scalare invariante sotto trasformazioni di Lorentz, il che è indubbiamente molto comodo seppur non strettamente necessario in quanto ci può capitare di dover descrivere sistemi non relativistici.

### Equazioni del moto

Limitiamoci ora ai casi di interesse fisico e consideriamo lagrangiane la cui dipendenza arriva solo alla derivata prima e imponiamo la stazionarietà dell'azione. Cioè $\delta A = 0$.
$$ 
\begin{aligned}
\delta A &= \int d^4 x  \left( \frac{ \partial \mathfrak{L} }{ \partial \phi_{k} } \delta \phi_{k}+\frac{ \partial \mathfrak{L} }{ \partial (\partial_{\mu }\phi_{k}) }\delta (\partial_{\mu }\phi_{k}) \right) \\
&=\int d^4x \; \left( \frac{ \partial \mathfrak{L} }{ \partial \phi_{k} } - \partial_{\mu} \frac{ \partial \mathfrak{L} }{ \partial (\partial_{\mu} \phi_{k}) } \right)\delta \phi_{k}+\partial_{\mu}\left( \frac{ \partial \mathfrak{L} }{ \partial (\partial_{\mu}\phi_{k}) }\delta \phi_{k}  \right)\\
&=\int d^4x\;\left( \frac{ \partial \mathfrak{L} }{ \partial \phi_{k} } - \partial_{\mu} \frac{ \partial \mathfrak{L} }{ \partial (\partial_{\mu} \phi_{k}) } \right)\delta \phi_{k} = 0
\end{aligned}
$$
il secondo termine è scomparso dopo essere stato trasportato fuori dall'integrale per il teorema fondamentale del calcolo integrale.
$\delta A = 0$ per ogni valore di x e t solo nel caso in cui siano soddisfatte le seguenti equazioni, per ogni valore di k.
$$
	\frac{ \partial \mathfrak{L} }{ \partial \phi_{k} } -\partial_{\mu}\frac{ \partial \mathfrak{L} }{ \partial (\partial_{\mu}\phi_{k}) } = 0
$$
Queste sono le equazioni del moto del nostro sistema fisico e sono in molti aspetti simili alle equazioni di Eulero-Lagrange che già conosciamo.
Riprendiamo l'esempio di prima: $\mathfrak{L} = -\frac{1}{2}(\partial_{\mu}\phi)(\partial^\mu \phi)-\frac{m^2}{2}\phi^2$ .
$$
	\begin{aligned}
	\frac{ \partial \mathfrak{L} }{ \partial \phi } &= -m^2\phi \\
	\frac{ \partial \mathfrak{L} }{ \partial (\partial_{\mu}\phi_{k}) } &= -\partial_{\mu}\phi  
	\end{aligned}
$$
Le equazioni di Eulero-Lagrange sono dunque:
$$
	\partial_{\mu}\partial^\mu \phi-m^2\phi=0
$$
### Sorgenti di campi

Spesso ci capita di dover studiare il comportamento dei campi in presenza di disturbi esterni e sorgenti. Per accomodare questo tipo di soluzione possiamo ad andare ad incorporare la sorgente direttamente all'interno della lagrangiana.
Possiamo introdurre una sorgente semplice nell'esempio usato fin'ora nel seguente modo:
$$
	\mathfrak{L}=-\frac{1}{2}(\partial_{\mu}\phi)(\partial^\mu \phi)-\frac{m^2}{2}\phi^2+\phi S(x)
$$
dove $S$ è una funzione del tempo e dello spazio. Imponendo la condizione di stazionarietà dell'azione ($\delta A=0$), otteniamo le stesse equazioni di Eulero-Lagrange trovate precedentemente, che si traducono nell'aggiunta della sorgente a destra dell'uguale:
$$
	\partial_{\mu}\partial^\mu \phi-m^2\phi = S
$$
## Domande aperte / cose da rivedere
- [ ] Cerca esempi online di come si arriva a questo formalismo partendo dal formalismo lagrangiano per il punto materiale
## Collegamenti
- Concetti collegati: [[]]

