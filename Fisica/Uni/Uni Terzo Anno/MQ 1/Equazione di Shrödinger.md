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
### Derivazione dell'equazione di Shrödinger

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

#### a) Particella libera NON-relativistica in 1-d

Cerchiamo una funzione d'onda:
$$
	\psi(x,t) \quad \text{t.c.} \quad \int^{x_{2}}_{x_{1}} dx|\psi(x,t)|^2=\text{ probabilità di trovare la particella tra } x_{1} \text{ e } x_{2} \text{ al tempo t}
$$
Come abbiamo discusso cerchimao un'PDE lineare per $\psi$ con coefficienti indipendenti da $p$ e $E$.
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
Ogni onda piana viene pesata dal coefficiente $A(k)$, inoltre, per il teorema di Plancherel, per funzioni normalizzabili vale la seguente uguaglianza:
$$
	\int_{-\infty}^{\infty}  \, dx \, |\psi(x)|^2 =\int_{-\infty}^{\infty}  \, dk \, |A(k)|^2 
$$
Questo ci suggerisce di interpretare $A(k)$ come un'ampiezza di probabilità per numeri d'onda e quindi per impulsi:
$$
\begin{aligned}
A(k)dk = &\text{probabilità di osservare un numero d'onda (e quindi un impulso } p=\hbar k \text{)} \\ &\text{in un intorno di larghezza } dk \text{ del valore di }k.
\end{aligned}
$$


## Domande per revisione
- [ ] 

## Collegamenti
- Lezione precedente: [[]]
- Concetti collegati: [[]]

