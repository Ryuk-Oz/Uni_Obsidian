---
corso: Meccanica Quantistica 1
data: 2026-09-29
tags:
  - lezione
argomenti:
  - Meccanica Quantistica
lezione-precedente: "[[Introduzione storica alla meccanica quantistica]]"
source:
---


> [!info] Contesto
> Corso: undefined
> Argomenti previsti: 

## Riassunto veloce



## Appunti

L'ultima cosa che abbiamo visto è l'esperimento della doppia fenditura, quello che ancora ci manca è un'interpretazione dei risultati sperimentali. Di questa si occupa la scuola di Copenhagen che ci fornisce la seguente interpretazione:
- Al moto delle particelle quantistiche è associata un'onda di probabilità, cioè una funzione $\psi(\vec{r},t)$ (funzione d'onda), che obbedisce ad un'equazione d'onda e il cui modulo quadrato $\rho(\vec{r},t)=|\psi(\vec{r},t)|^2$ rappresenta la densità di probabilità della posizione della particella.
$$
	\rho(\vec{r},t)d^3r =\text{ probabilità di trovare la particella in } d^3r
\text{ al tempo } t$$
Per la prima volta la probabilità non entra in gioco sotto forma di incertezza sperimentale, bensì si manifesta in termini di principi primi.
Occupiamoci dunque della ricerca dell'equazione che ci fornisce la funzione d'onda $\psi$
#### 1. Argomentazioni empiriche verso l'equazione di Shrödinger

Partiamo da alcune considerazioni sulle leggi fisiche in generale.
Tutte le equazioni fondamentali della fisica **NON** vengono "derivate". Sono bensì postulate sulla base dell'evidenza empirica, dell'eleganza e della generalità. In seguito vengono verificate sperimentalmente fino a venire, in ultimo, falsificate.

Sulla base di queste considerazioni, vediamo quali sono gli "input" empirici e quali le conseguenze che ne possiamo trarre per andare a ricostruire la nostra equazione.

| INPUT                                                                                                                             | OUTPUT                                                                                                     |
| --------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Esperimento di difrazzione di particelle elementari                                                                               | A ogni particella è associata un'onda di probabilità                                                       |
| Ipotesi di Planck + Einstein (RS) + De Broglie, che portano a dire che per una particella $p=\frac{h}{\lambda} \text{ e } E=h\nu$ | A oggetti con $p$ e $E$ definiti associo onde con $\lambda$ e $\nu$ definiti, e queste onde interferiscono |

Possiamo fare ulteriori considerazioni andando a costruire un'onda di $\lambda$ definita, del tipo $\sin(kx)=\sin\left( \frac{2\pi}{\lambda} x \right)$,  e otteniamo un risultato di questo tipo:

![[Pasted image 20260929231216.png]]

Dall'interpretazione di copenhagen sappiamo che $|\psi\\^2|$ rappresenta la densità di probabilità che la particella si trovi in $x$ a un certo tempo $t$ fissato.
Dunque una particella a cui associo un'onda di probabilità con $\lambda$ definita potrebbe "trovarsi ovunque".
Analogamente fissando $\nu$ la particella potrebbe trovarsi in un qualunque istante nel tempo.

Però a noi interessano delle soluzioni che siano localizzate, come facciamo?
Posso costruire delle soluzioni localizzate tramite un "principio di sovrapposizione" andando a considerare dei pacchetti d'onda localizzati nello spazio e nel tempo, e $\lambda$ e $\nu$ andranno a ricadere in un intervallo di valori.
Affinchè una sovrapposizione del genere sia possibile, abbiamo bisogno che l'equazione differenziale dell'onda sia lineare (questa stessa linearità farà poi emergere una struttura di spazio vettoriale).
Non solo, devo anche poter andare a sovrapporre onde con $\lambda$ e $\nu$ diversi, a causa dell'ipotesi di De Broglie. Questo equivale ad avere $p$ e $E$ diversi. Dunque tra i coefficienti dell'equazione differenziale non possono comparire termini che dipendano da $p$ e $E$ (termini di natura cinematica), perchè andrebbero a fissare soluzioni ad una lunghezza d'onda e ad una frequenza ben definite.

#### 2. Equazione per la particella libera NON-relativistica in 1-d

Cerchiamo una funzione d'onda:
$$
	\psi(x,t) \quad \text{t.c.} \quad \int^{x_{2}}_{x_{1}} dx|\psi(x,t)|^2=\text{ probabilità di trovare la particella tra } x_{1} \text{ e } x_{2} \text{ al tempo t}
$$
Come abbiamo discusso cerchimao una PDE lineare per $\psi$ con coefficienti indipendenti da $p$ e $E$.
L'intereferenza per 2 fenditure dev'essere analoga a quella dell'esperimento di Young, cerchiamo dunque soluzioni periodiche, del tipo:
$$
	\begin{aligned}
	\psi_{1}(x,t)&=A_{1}\cos(kx-\omega t) \\
	\psi_{2}(x,t)&=A_{2}\sin(kx-\omega t) \\
	\text{o in generale:} &\quad \psi_{\pm}(x,t) = B_{\pm}e^{\pm i(kx-\omega t)}
	\end{aligned}
$$
##### Tentativo 1
Iniziamo con un Ansatz ragionevole, partendo da qualcosa di noto, l'equazione di D'Alambert.
$$
	\frac{ \partial^2 \psi }{ \partial t^2}=\gamma \frac{ \partial^2 \psi }{ \partial x^2 }  
$$
sappiamo già che questa non va bene, poichè il parametro $\gamma=\frac{1}{v^2}$ ha natura cinematica. Andiamo comunque a verificarlo per motivi didattici.
$$
	\begin{aligned}
	\frac{ \partial^2 \psi_{2} }{ \partial t^2 }&=-\omega^2 \psi_{1} \\
	\frac{ \partial^2 \psi_{1} }{ \partial x^2 }&=-k^2\psi_{1}\\
	\implies -\omega^2\psi_{1}&=\gamma(-)k^2\psi_{1} 
	\end{aligned}
$$
cioè:
$$
	\gamma=\frac{\omega}{k}=\frac{E^2}{p^2}= \frac{p^2}{4m^2}
$$
dipende da termini cinematici, idem per $\psi_{2}$ e $\psi_{\pm}$.

Notiamo però alcune cose:
$$
	\begin{aligned}
	\frac{ \partial  }{ \partial t } \propto \omega \quad \text{;}\quad \frac{ \partial  }{ \partial x } \propto k 
	\end{aligned}
$$
e:

$$
	E=\frac{p^2}{2m}=\frac{\hbar^2k^2}{2m}=h \nu=\hbar \omega \implies \omega=\frac{{\hbar k^2}}{2m}
$$
cioè a una $\frac{ \partial  }{ \partial t }$ corrispondono DUE $\frac{ \partial  }{ \partial x }$.

##### Tentativo 2

Cerco qualcosa in una derivata temporale e due derivate spaziali, come l'equazione del calore.
$$
	\frac{ \partial \psi }{ \partial t }=\gamma \frac{ \partial^2 \psi }{ \partial x^2 }  
$$
Verifichiamo se va bene:
- Caso $\psi_{1}$:
$$
	\frac{ \partial \psi_{1} }{ \partial t }= \omega \psi_{2} \quad \text{ ; } \quad\frac{ \partial^2 \psi_{1} }{ \partial x^2 }=-k^2\psi_{1}  
$$
dunque $\psi_{1}$ non è soluzione.
Anlogamente ottengo che $\psi_{2}$ non è soluzione.

Proviamo a studiare la soluzione generale in forma esponenziale:
$$
	\frac{ \partial \psi_{\pm} }{ \partial t }=\mp i\omega \psi_{\pm} \quad \text{ ; } \quad \frac{ \partial^2 \psi_{\pm} }{ \partial x^2 }=-k^2\psi\pm  
$$

Sostituendo nell'equazione otteniamo:
$$
	\mp i\omega=\gamma(-k^2) \implies \gamma=\pm \frac{i\omega}{k^2}=\pm i \frac{{\hbar k^2}}{2m} \frac{1}{k^2}=\pm \frac{i\hbar}{2m}
$$
In questo caso $\gamma$ non dipende da termini cinematici, dunque va bene.

- **OSS 1:** l'equazione funziona ammettendo che $\psi$ sia una funzione a variabili complesse dunque i numeri complessi dunque smettono di essere un mero strumento matematico opzionale ma sono intrinsechi al nostro modello.
- **OSS 2:** ho un ambiguità di segno ma questa non è assolutamente problematica, cambiare segno all'equazione equivale semplicemente a trovare la soluzione complessa coniugata.

A questo punto possiamo scrivere la nostra equazione.

>[!Summary] Equazione di Shrödinger per particelle libere in $d=1$
> 
> $$
>	i\hbar \frac{ \partial \psi }{ \partial t }= -\frac{\hbar^2}{2m}\frac{ \partial^2 \psi }{ \partial x^2 }  
> $$

Quest'equazione ammette soluzioni di energia e impulso ben definite, dunque di $\lambda$ e $\omega$ definite:
$$
	\psi_{\lambda \nu} =Ae^{i(kx-\omega t)} \quad\omega=\frac{{\hbar k^2}}{2m}
$$

Inoltre le soluzioni di interesse fisico devono essere tali che:
- $\psi(x,t)$ sia continua e differenziabile quanto basta
- $\psi(x,t)$ sia MONODROMA, perchè il valore della probabilità dev'essere univoco
- $\psi(x,t)$ sia al quadrato sommabile sul laboratorio $\in L^2(\text{lab})$, infatti, per definizione: 
  $$
	  	\exists \; \int_{\text{lab}}\text{"}dx\text{"} |\psi(x,t)|^2
  $$
essendo $|\psi|^2$ una densità di probabilità

L'interpretazione probabilistica e la richiesta di normalizzabilità portano con se 2 problemi, uno di natura concreta e uno di natura formale

- **Problema concreto**, le soluzioni con $\lambda$ e $\nu$ definiti sono tali che:  
$$
   	|\psi_{\lambda \nu}(x,t)|^2=\text{cost}
$$
per cui risultano **completamente delocalizzate** nel volume accessibile (il laboratorio).
Questo è facilmente risolvibile andando a costruire dei "pacchetti d'onda" localizzati sfruttando la lineraità delle equazioni.

- **Problema formale**, nel limite di volume accessibile $\infty$ ($L\to \infty$ in $d=1$) , le soluzioni per onde piane $\psi_{\lambda \nu}$ **NON** sono normalizzabili. Questo richiederà particolare attenzione quando andremo a lavorare in limiti sì comodi, ma anche assai problematici, come questo.
In merito a ciò, è sempre bene tenere a mente che nella realtà tutti i laboratori hanno estensione FINITA e tutti i processi di misura sono DISCRETI. Dunque questo problema è un problema formale che riguarda puramente la matematica che utilizziamo per studiare il fenomeno e non l'interpretazione fisica in se.

Studiamo ora l'equazione tramite l'utilizzo di operatori differenziali che ci permettono di fare luce sull'interpretazione fisica.

Partiamo dalle soluzioni a impulso e energia definiti.
$$
	\psi_{p,E}(x,t)=Ae^{i(kx-\omega t)}; \quad p=\hbar k, \; E=\hbar \nu
$$
Studio l'azione del termine di derivata temporale:
$$
	i\hbar \frac{ \partial  }{ \partial t } \psi_{p,E}(x,t) = i\hbar(-i\omega)\psi_{p,E}(x,t)=E\psi_{p,E}(x,t) 
$$
dunque $\psi_{p,E}$ è un autofunzione dell'operatore $i\hbar \frac{ \partial  }{ \partial t }$ all'autovalore $E$.

Studiamo adesso l'azione della singola derivata spaziale:
$$
	-i\hbar \frac{ \partial  }{ \partial x } \psi_{p,E}(x,t) = -i\hbar(ik)\psi_{p,E}(x,t)=p\psi_{p,E}(x,t)
$$
dunque $\psi_{p;E}$ è anche autofunzione dell'operatore $\hat{p}=-i\hbar \frac{ \partial  }{ \partial x }$ con autovalore $p$.

Studiando la seconda derivata spaziale otteniamo:
$$
	-\frac{\hbar^2}{2m}\frac{ \partial^2  }{ \partial x^2 }\psi_{p,E}(x,t)=\frac{p^2}{2m}\psi_{p,E}(x,t) 
$$
cioè $\psi_{p,E}$ è autofunzione dell'operatore $\hat{K}=-\frac{\hbar^2}{2m} \frac{ \partial^2  }{ \partial x^2 }$ con autovalore $K=\frac{p^2}{2m}$.

Dunque vale l'uguaglianza $E\psi_{p,E}=K\psi_{p,E}$ e $E=K$. Il che è ragionevole visto che stiamo studiando l'equazione per la particella libera.

##### Soluzione generale dell'equazione per particella libera in $d=1$

Per estrarre ricavare la soluzione generale dell'equazione:
$$
	i\hbar \frac{ \partial \psi }{ \partial t }= -\frac{\hbar^2}{2m}\frac{ \partial^2 \psi }{ \partial x^2 }  
$$
sfruttiamo le trasformate di Fourier.
Riscriviamo $\psi(x,t)$ come:
$$
	\psi(x,t)=\frac{1}{\sqrt{ 2\pi }}\int^{+\infty}_{-\infty}dk A(k,t) e^{ikx}
$$
andiamo a derivarla:
$$
	\begin{aligned}
	i\hbar \frac{ \partial \psi }{ \partial t }&=\frac{1}{\sqrt{ 2\pi }}\int_{-\infty}^{\infty}  \, dk \, \left( i\hbar \frac{ \partial A }{ \partial t } \right)e^{ikx} \\
	-\frac{\hbar^2}{2m}\frac{ \partial^2 \psi }{ \partial x^2 } &= \frac{1}{\sqrt{ 2\pi }}\int_{-\infty}^{\infty}  \, dk  \, A(k,t) (ik)^2 (-) \frac{\hbar^2}{2m}e^{ikx}\\
	\implies  \frac{1}{\sqrt{ 2\pi }}&\int_{-\infty}^{\infty}  \, dk \, e^{ikx} \left( i\hbar \frac{ \partial A }{ \partial t } -\frac{\hbar^2k^2}{2m} A(k,t) \right) =0
	\end{aligned}
$$
l'integrale deve annullarsi per ogni $x$ e $t$, dunque:
$$
	\begin{aligned}
	i\hbar \frac{ \partial A }{ \partial t } &= \frac{\hbar^2k^2}{2m}A(k,t) \\
	\to \frac{ \partial A }{ \partial t }=-i&\frac{\hbar k^2}{2m} A(k,t)=-i\omega(k)A
	\end{aligned}
$$

Risolvendo quest'equazione più semplice otteniamo:
$$
	A(k,t)=A(k,0)e^{-i\omega t}
$$
Sostituiamo all'interno dell'antitrasformata:
$$
	\psi(x,t)=\frac{1}{\sqrt{ 2\pi }}\int_{-\infty}^{\infty}  \, dk \, A(k)e^{i(kx-w(k)t)} \quad \omega=\frac{{\hbar k^2}}{2m}
$$
e:
$$
	\psi(x,0)=\frac{1}{\sqrt{ 2\pi }}\int_{-\infty}^{\infty}  \, dk \, A(k)e^{ikx}
$$
Interpretiamo la soluzione generale come una sovrapposizione di onde piane con numeri d'onda $k$ (e di conseguenza impulsi $p$) diversi.
Ogni onda piana viene pesata dal coefficiente $A(k)$, inoltre, per il teorema di Plancherel, per funzioni normalizzabili vale la seguente uguaglianza (equazione di Parseval):
$$
	\int_{-\infty}^{\infty}  \, dx \, |\psi(x)|^2 =\int_{-\infty}^{\infty}  \, dk \, |A(k)|^2 
$$
Questo ci suggerisce di interpretare $A(k)$ come un'ampiezza di probabilità per numeri d'onda e quindi per impulsi:
$$
\begin{aligned}
A(k)dk = &\text{probabilità di osservare un numero d'onda (e quindi un impulso } p=\hbar k \text{)} \\ &\text{in un intorno di larghezza } dk \text{ del valore di }k.
\end{aligned}
$$

Accantoniamo momentaneamente i problemi legati alle soluzioni "fondamentali" delle onde piane e occupiamoci della costruzione di una classe di soluzioni che rappresentano particelle **localizzate** e studiamone l'interpretazione fisica e l'evoluzione temporale, i pacchetti d'onde gaussiani.

##### Pacchetto d'onda gaussiano

Partiamo dalla costruzione delle condizioni iniziali della nostra onda. Prendo come **condizione iniziale** una forma localizzata, in particolare una gaussiana:
$$
	\psi(x,0)=Ne^{ -x^2/a^2 } \quad a=\text{semilarghezza}
$$
![[Pasted image 20261002110437.png|278]]
Normalizziamo $\psi$, in accordo con l'interpretazione probabilistica.
$$
	\begin{aligned}
	1=\int_{-\infty}^{\infty}  \, dx \, |\psi(x,0)|^2=N^2\int_{-\infty}^{\infty}  \, dx \, e^{ -2x^2/a^2 } &\underset{y\equiv \frac{\sqrt{ 2 }}{a}x}{=}N^2 \frac{a}{\sqrt{ 2 }}\int_{-\infty}^{\infty}  \, dy \,e^{ -y^2 }=N^2 a\sqrt{ \frac{\pi}{2} }\\
	\implies N&=  \left( \frac{2}{\pi a^2} \right)^{1/4}
	\end{aligned}
$$
In generale $N$ sarebbe complesso ma lo scegliamo reale perchè la quantita che misuriamo, $|\psi|^2$ è reale.

Calcoliamo a questo punto i **momenti** della nostra distribuzione di probabilità.
- VALOR MEDIO di $x$: 
  $$
  	<x> \equiv \int_{-\infty}^{\infty}  \, dx \, x\,|\psi(x,0)|^2=0 \quad \text{per simmetria}
  $$
- VALOR MEDIO di $x^2$:
  $$
\begin{aligned}
<x^2> &\equiv \int_{-\infty}^{\infty}  \, dx \, x^2 \, |\psi(x,0)|^2 \underset{\alpha \equiv \frac{2}{a^2}}{=} N^2 \int_{-\infty}^{\infty}  \, dx \, x^2 e^{ -\alpha x^2 }\\
&=N^2\left( -\frac{d}{d\alpha} \right)\int_{-\infty}^{\infty}  \, dx \,e^{ \alpha x^2 }=N^2\left( -\frac{d}{d\alpha} \right)\sqrt{ \frac{\pi}{\alpha} }\\
&=N^2 \frac{\sqrt{ \pi }}{2}\alpha^{-3/2}= \frac{1}{a}\sqrt{ \frac{2}{\pi} } \frac{\sqrt{ \pi }}{2} \frac{a^2}{2}\sqrt{ \frac{a^2}{2} }=\frac{a^2}{4}
\end{aligned}	
  $$
  - DEV. STD. di $x$: $$
 	\Delta x\equiv \sqrt{ <x^2>-<x>^2 }=\sqrt{ <x^2> }=\frac{a}{2}
    $$
$\Delta x$ misura l'incertezza sulla posizione della particella a $t=0$.

Per studiare l'evoluzione di queste condizioni iniziali nel tempo, compatibilmente all'equazione di Shrödinger andiamo a ricostruire la trasformata di Fourier $A(k,t)$, ricordando che 
$$
	A(k,t)=A(k,0)e^{ i(kx-\omega(k))t }
$$
Cerchiamo dunque $A(k,0)$.
Per definizione:
$$
	\psi(x,0)=\frac{1}{\sqrt{ 2\pi }}\int_{-\infty}^{\infty}  \, dk \, A(k,0)\,e^{ ikx }
$$
da cui:
$$
	A(k,0)=\frac{1}{\sqrt{ 2\pi }} \int_{-\infty}^{\infty}  \, dx \, \psi(x,0)\,e^{ -ikx }
$$

Se $\psi\in L(-\infty,+\infty)$ allora $A(k)$ è normaliz mkzabile come $\psi(x)$:
$$
	\int_{-\infty}^{\infty}  \, dk \, |A(k)|^2 \equiv||A|| =\int_{-\infty}^{\infty}  \, dx \, |\psi(x)|^2 \equiv ||\psi||
$$
E possiamo dunque calcolare $A(k)$.
$$
	\begin{aligned}
	A(k)&=\frac{N}{\sqrt{ 2\pi }}\int_{-\infty}^{\infty}  \, dx \, e^{- \frac{x^2}{a^2}-ikx}
	\end{aligned}
$$
sostituisco $-\frac{x^2}{a^2}-ikx=-\left( \frac{x}{a}-\frac{ika}{2} \right)^2-\frac{k^2a^2}{4}$:
$$
\begin{aligned}
A(k)&= \frac{N}{\sqrt{ 2\pi }}\int_{-\infty}^{\infty}  \, dx \, e^{-\left( \frac{x}{a}+\frac{ika}{2} \right)^2}e^{ -k^2a^2/4 }\underset{y=\frac{x}{a}+\frac{ika}{2}}{=}\frac{Na}{\sqrt{ 2 }}e^{ -k^2a^2/4 }=\\
&\underset{\text{Sost. }N}{=}\left( \frac{2}{\pi} \right)^{1/4}a^{-1/2} \frac{a}{\sqrt{ 2 }}e^{ -k^2a^2/4 }=\left( \frac{2}{\pi} \right)^{1/4}\sqrt{ \frac{a}{2} }e^{-k^2a^2/4}
\end{aligned}
$$
**Oss:** è correttamente normalizzata, come si può facilmente verificare sostituendo $k\to x$ e $\frac{2}{a}\to a$, osservando che si riottiene esattamente $\psi(x)$. Inoltre, come visto a metodi, la trasformata di Fourier di una Gaussiana di semilarghezza $a$ è una Gaussiana di semilarghezza $\frac{2}{a}$.

Da qua otteniamo anche una **relazione di indeterminazione** per $t=0$.
$$
	\Delta x=\frac{a}{2} \Leftrightarrow \Delta k=\frac{1}{a} \implies \Delta p=\hbar \Delta k=\frac{\hbar}{a}
$$
L'interpretazione probabilistica di $A(k)$ implica dunque che per un pacchetto gaussiano a $t=0$:
$$
	\Delta x\cdot \Delta p=\frac{\hbar}{2}
$$
primo esempio di relazione di indeterminazione (si tartta di una relazione al minimo, in generale vedremo $\Delta x\cdot \Delta p\geq \frac{\hbar}{2}$).
Questo risultato è una conseguenza diretta dell'interpretazione probabilistica di $\psi(x)$ e $A(k)$ unita alla proprietà delle trasformate di Fourier che ci dice che per costruire un'onda localizzata occorre far interferire molte onde di $\lambda$ diverse mentre le onde monocromatiche sono completamente delocalizzate.

Ora che abbiamo $A(k)$ possiamo ricavare $A(k,t)$ e di conseguenza $\psi(x,t)$. Definiamo $\Delta x_{0}\equiv \frac{a}{2}$.
Riscrivo $A(k)$ nel seguente modo:
$$
	A(k)=N\sqrt{ 2 }\Delta x_{0}\exp[-k^2\Delta x_{0}^2]
$$
Allora:
$$
	\begin{aligned}
	\psi(x,t)&=\frac{1}{\sqrt{ 2\pi }}\int_{-\infty}^{\infty}  \, dk \, A(k)e^{ i(kx-w(k)t) }=\\
	&=\frac{N\Delta x_{0}}{\sqrt{ \pi }}\int_{-\infty}^{\infty}  \, dk \,\exp\left[ -k^2\Delta x_{0}^2-i\hbar \frac{k^2}{2m}t+ikx \right]=\\
	&=\frac{N\Delta x_{0}}{\sqrt{ \pi }}\int_{-\infty}^{\infty}  \, dk \,\exp[-k^2B^2+ikx]
	\end{aligned}
$$
dove $B^2\equiv \Delta x_{0}^2+\frac{i\hbar}{2m}t$.
Completiamo il quadrato:
$$
	\psi(x,t)=\frac{N\Delta x_{0}}{\sqrt{ \pi }}e^{ -\frac{x^2}{4B^2} }\int_{-\infty}^{\infty}  \, dk \exp\left[ -\left( Bk-\frac{ix}{2B} \right)^2 \right]=\frac{N\Delta x_{0}}{B}\exp\left[ -\frac{x^2}{4B^2} \right]
$$
nel passaggio finale abbiamo risolto l'integrale gaussiano ponendo $y\equiv Bk-\frac{ix}{2B}$.
Abbiamo ottenuto una funzione d'onda complessa (perchè $B$ è complesso).

Paragoniamo la densità di probabilità di posizioni (REALI) a $t=0$ e $t$ generico:
$$
	\rho(x,0)=|\psi(x,0)|^2=N^2\exp\left[ -\frac{x^2}{2\Delta x_{0}^2} \right] \implies N^2=\frac{1}{\sqrt{ 2\pi }} \frac{1}{\Delta x_{0}}
$$
(troviamo che $a=\Delta x_{0}$)
Invece per $\rho(x,t)$ l'esponenziale è complesso e dobbiamo moltiplicarlo per il proprio complesso coniugato:
$$
	\begin{aligned}
	\rho(x,t)=|\psi(x,t)|^2&=\frac{N^2\Delta x_{0}^2}{|B|^2}\exp\left[ -\frac{x^2}{4B^2}-\frac{x^2}{4(B^*)^2} \right]=\\
	&=\frac{N^2\Delta x_{0}^2}{|B|^2}\exp\left[ -\frac{x^2}{4} \frac{(B^*)^2+B^2}{|B|^4} \right]=\\
	&=\frac{N^2\Delta x_{0}^2}{|B|^2}\exp\left[ -\frac{x^2}{2} \frac{\mathrm{Re}(B^2)}{|B|^4} \right]
	\end{aligned}
$$
Calcoliamo $\mathrm{Re}(B^2)$ e $|B|^4$:
$$
	\begin{aligned}
	B^2=\Delta x_{0}^2+\frac{i\hbar}{2m}t &\implies \mathrm{Re}(B^2)=\Delta x_{0}^2\\
	(B^*)^2=\Delta x_{0}^2-\frac{i\hbar}{2m}t&\implies |B|^4=\Delta x_{0}^4\left( 1+\frac{\hbar^2}{4m^2\Delta x_{0}^2}t^2 \right)
	\end{aligned}
$$
dunque:
$$
	\frac{\mathrm{Re}(B^2)}{2|B|^4}=\frac{1}{2\Delta x_{0}^2} \frac{1}{1+\frac{\hbar^2t^2}{4m^2\Delta x_{0}^4}}
$$
definiamo $\Delta x_{t}$ come:
$$
	\Delta x_{t}\equiv \Delta x_{0}\sqrt{ 1+\frac{\hbar^2t^2}{4m^2\Delta x_{0}^4} }
$$
E possiamo riscrivere:
$$
	|B|^2=\sqrt{ (\mathrm{Re}(B^2))^2+(\mathrm{Im}(B^2))^2 }=\sqrt{ \Delta x_{0}^4+\frac{\hbar^2t^2}{4m^2} }=\Delta x_{0}^2\sqrt{ 1+\dots }=\Delta x_{0}\cdot \Delta x_{t}
$$
da cui:
$$
	\rho(x,t)=N^2 \frac{\Delta x_{0}}{\Delta x_{t}}\exp\left[ -\frac{x^2}{2(\Delta x_{t})^2} \right]
$$

**OSSERVAZIONI sui risultati ottenuti:**
- $\rho(x,t)$ è correttamente normalizzata $\forall t$ e resta gaussiana, Risolvendo l'integrale e normalizzando otteniamo: 	$$N^2=\frac{1}{\sqrt{ 2\pi }} \frac{1}{\Delta x_{0}}$$ Dunque il fattore $\frac{\Delta x_{0}}{\Delta x_{t}}$ è quello che ci permette di mantenere la stessa normalizzazzione sostituendo la vecchia semilarghezza $\Delta x_{0}$ con la nuova $\Delta x_{t}$.
- $\Delta x_{t}>\Delta x_{0} \forall \, t$ (sia $t>0 \text{ che }t<0$). Dunque l'indeterminazione sulla posizione aumenta nel tempo. La gaussiana si abbassa e si allarga.
- Nel caso di particella libera l'indeterminazione sull'impulso resta invece COSTANTE nel tempo: 
  $$
  	A(k,t)=A(k,0)e^{-i\omega t} \implies |A(k,t)|^2=|A(k,0)|^2
  $$
  cioè 
  $$
	\Delta p_{t}=\Delta p_{0}=\hbar \Delta k_{0}\equiv \frac{\hbar}{2\Delta x_{0}} \quad \text{ricordandoci che } \Delta k_{0}=\frac{1}{a}=\frac{1}{2\Delta x_{0}}
  $$
Utilizzando un'argomentazione semiclassica possiamo spiegare queste osservazioni ricordandoci di avere ottenuto il pacchetto da una sovrapposizione di onde con numeri d'onda diverse, cioè diversi impulsi, e dunque diverse velocità di propagazione (velocità classiche). Quindi le componenti del pacchetto si allontanano dall'origine a velocità diverse e non nulle. 
$$
	\Delta x_{t}=\sqrt{ \Delta x_{0}^2 +\frac{\hbar^2t^2}{4m^2\Delta x_{0}^2}} \quad \text{ e } \quad \frac{\hbar^2t^2}{4m^2\Delta x_{0}^2}\underset{\Delta p=\frac{\hbar}{2\Delta x}}{=} \left( \frac{\Delta p_{0}}{m}t \right)^2\equiv(\Delta v_{0}\cdot t)^2
$$
cioè l' incertezza sulla posizione aumenta col tempo come:
$$
	\Delta x_{t}=\sqrt{ \Delta x_{0}^2 + (\Delta v_{0}t)^2 }
$$
Che è la somma in quadratura di due incertezze indipendenti, una sulle velocità e una sulle posizioni. Capiamo dunque che l'incertezza sulle posizioni è dovuta all'intervallo $\Delta v_{0}$ di velocità iniziali. L'argomentazione è semiclassica perchè stiamo sfruttando $p=mv$.

Di fronte a queste osservazioni, i nostri risultati sono abbastanza deludenti. La gaussiana si allarga e si abbassa ma NON SI SPOSTA. Questo non ci stupisce, infatti abbiamo scelto delle condizioni iniziali tali che $<k> = <p> =0$ (si ottiene facilmente per simmetria come fatto per $<x>$.
Pertanto, al fine di ottenere un pacchetto di onde in moto, ci basta andare a cambiare le condizioni iniziali di $A(k)$:
$$
	A(k,0)\propto \exp\left[ -\frac{k^2a^2}{4} \right]\to A(k,0)\propto \exp\left[ -\frac{a^2}{4} (k-k_{0})^2 \right]
$$
il valore medio di $<k>$ diventa $<k> = k_{0} \implies <p> = \hbar k_{0}$.
Svolgendo i calcoli si vede che la risultante $\rho(x,t)$ si muove con velocità media $\frac{<p>}{m}$ e durante il moto la gaussiana si allarga come nel caso preso in esame prima. Per i calcoli del pacchetto in moto vedere l'appendice.
Il risultato esposto graficamente è:
![[Pasted image 20261003125732.png]]
Facciamo alcune osservazioni sui valori medi in termini di $\psi$ e $A$.
Sappiamo che le informazioni codificate dalla funzione d'onda sono ugualmente codificate dalla sua trasformata di Fourier, guardiamo come questo si traduce nella codificazione dei valori medi.

- Nello "spazio x": 
  $$
  	<x> \equiv \int_{-\infty}^{\infty}  \, dx \, x|\psi(x,t)|^2
 \implies<f(x)> \equiv \int_{-\infty}^{\infty}  \, dx \, f(x) |\psi(x,t)|^2  $$
 - Nello "spazio k": 
   $$
   	<p> = \hbar<k> = \hbar \int_{-\infty}^{\infty}  \, dk \, k |A(k,t)|^2
\implies <f(p)> \equiv \int_{-\infty}^{\infty}  \, dk \,f(\hbar k)|A(k,t)|^2   $$
Per descrivere $<p>$ nello "spazio x" usiamo nuovamente Fourier.
$$
	\begin{aligned}
	<p>&=\hbar \int_{-\infty}^{\infty}  \, dk \, |A(k,t)|^2=\\
	&=\frac{\hbar}{2\pi}\int_{-\infty}^{\infty}  \, dk \, k\int_{-\infty}^{\infty}  \, dx \, \psi(x,t)e^{ -ikx }\int_{-\infty}^{\infty}  \, dy \, \psi^*(y,t)e^{ iky } \quad \left( =\int_{-\infty}^{\infty}  \, dk \, k A\cdot A^* \right) =\\
	&=\frac{\hbar}{2\pi}\int_{-\infty}^{\infty}   \int_{-\infty}^{\infty}  \, dx \, dy\, \psi(x,t)\psi^*(y,t)\int_{-\infty}^{\infty}  \, dk \, k\,e^{ -ik(x-y) }=\\
	&=\frac{\hbar}{2\pi}\int_{-\infty}^{\infty} \int_{-\infty}^{\infty}  \, dx \, dy\, \psi \,\psi^* \int_{-\infty}^{\infty}  \, dk \, \left( -i \frac{ \partial  }{ \partial x } \right) e^{ -ik(x-y) }=\\
	&=\frac{\hbar}{2\pi}\int_{-\infty}^{\infty}  \, dy \, \psi^*(y,t) \int_{-\infty}^{\infty}  \, dx \, \left( -i\frac{ \partial  }{ \partial x } \right)\psi(x,t) \int_{-\infty}^{\infty}  \, dk e^{ -ik(x-y) }=\\
	&=\frac{\hbar}{2\pi}\int_{-\infty}^{\infty}  \, dy \, \psi^*(y,t) \int_{-\infty}^{\infty}  \, dx \, \left( -i\frac{ \partial  }{ \partial x }  \right)\psi(x,t) \, 2\pi \delta(x-y)=\\
	&=\int_{-\infty}^{\infty}  \, dx \, \psi^*(x,t) \left( -i\hbar \frac{ \partial  }{ \partial x } \right)\psi(x,t)=\\
	&=\int_{-\infty}^{\infty}  \, dx \,  \hat{p} \,( |\psi(x,t)|^2)
	\end{aligned}
$$
Cioè, nello "spazio x" l'impulso $p$ è rappresentato dall'operatore differenziale.
$$
	\hat{p}\equiv-i\hbar \frac{ \partial  }{ \partial x } 
$$
Analogamente si può mostrare che nello "spazio $k$" la posizione è rappresentata dall'operatore:
$$
	\hat{x}\equiv+i\frac{ \partial  }{ \partial k } 
$$


## Domande per revisione
- [ ] 

## Collegamenti
- Lezione precedente: [[]]
- Concetti collegati: [[]]

