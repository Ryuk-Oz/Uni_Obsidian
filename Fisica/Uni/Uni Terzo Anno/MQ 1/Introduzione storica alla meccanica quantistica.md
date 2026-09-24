---
corso: Meccanica Quantistica 1
data: 2026-09-21
tags:
  - lezione
argomenti: []
lezione-precedente:
source:
---


> [!info] Contesto
> Corso: Meccanica Quantistica 1
> Argomenti previsti: Introduzione storica alla meccanica quantistica, corpo nero, effetto fotoelettrico, effeto compton, primi modelli atomici

## Riassunto veloce

.In questa prima parte diamo un'introduzione storica alla meccanica quantistica, contestualizzandone la nascita.
Per farlo studiamo una serie di osservazioni sperimentali e problemi inspiegabili classicamente e vediamo come si risolvono attraverso la quantizzazione. In particolare guardiamo allo studio della radiazione del corpo nero e le leggi che erano state formulate per spiegarla:
Stephan-Boltzmann -> Wien -> Rydberg-Wien -> Planck.
Subito dopo abbiamo analizzato l'effetto fotoelettrico e la soluzione proposta da Einstein, che abbandona l'assolutezza delle equazioni di Maxwell.
Abbiamo poi visto l'effetto Compton e come questo venga risolto andando a quantizzare la luce in pacchetti di onde che chiamiamo fotoni e che trattiamo come particelle prive di massa.
Infine siamo andati a studiare il ramo della spettroscopia degli atomi vedendo la nascita dei primi modelli atomici. Per primo il modello a panettone di Thomson, confutato da Rutherford che scopre che la materia è prevalentemente vuota e poi il modello planetario di Bohr che risolve il problema della decaduta dell'$e^-$ andando a "bloccarlo" su orbite privilegiate, di energia quantizzata, sulle quali l'elettrone non emette radiazione.
## Appunti

Lo sviluppo della meccanica quantistica inizia nel '900, secolo in cui avvengono due rivoluzioni scientifiche:
- Relatività (RR-1905 e RG-1915)
- Meccanica Quantistica (1900-Planck ~ 1927)
Le due verranno poi unite nella QFT che però lascia fuori la RG.
La meccanica quantistica è importante per vari motivi, in particolare spiega fenomeni macroscopici altrimenti inspiegabili:
- stabilità della materia
- indistinguibilità degli atomi
- la tavola periodica $\to$ chimica e le altre branche della fisica collegate, come la fisica della materia, la fisica atomica e molecolare e lo studio di superfluidità e supercriticità
Ulteriormente la meccanica quantistica è dotat di un fortissimo potere predittivo, come si può evincere dalla precisione nel calcolo del momento magnetico anomalo dell'$e^-$ (precisione di $10^{-12}$).
Tuttavia la meccanica quantistica presenta il problema di essere **FORTEMENTE** controintuitiva. tanto da far sorgere tutt'ora dibattiti sulla sua interpretazione.

### Contesto Storico
Prima del '900 avevamo fondamentalmente 2 teorie della fisica classica che coprivano la stragrande maggioranza dei fenomeni in maniera molto efficace:
- **Meccanica dei corpi materiali** (Newton, Lagrange, Hamilton), che permetteva di descrivere i moti planetari e la cinetica dei Gas e che portò alla scoperta dell'elettrone (Thompson) e alla previsione teorica dell'esistenza di Nettuno (Le Verrier).
- **Teoria dei campi classica** (elettromagnetismo di Maxwell), che si occupa dello studio di onde e campi unendo i fenomeni elettrici, magnetici e ottici.
Queste teorie funzionano così bene che nel 1894 Albert Michelson afferma che tutte le leggi fisiche importanti siano già state scoperte e che la materia possa spostarsi solo verso i calcoli di precisione da ora in avanti, e nel 1900 Lord Kelvin afferma che gli unici problemi rimasti fossero il teorema di equipartizione e quello del moto dei corpi attraverso l'etere. 
Entrambi saranno smentiti da una serie di esperimenti che avverranno a cavallo di quegli anni.

#### Radiazione del corpo nero

Partiamo da un fatto empirico, scaldando un corpo questo cambia colore (passando dall'infrarosso all'ultravioletto, cioè aumentando la propria frequenza).
Dunque la materia emette radiazione.
Definisco una funzione $\varepsilon(\nu,T)$, intensità della radiazione emessa dal corpo in funzione della frequenza della radiazione e della temperatura del corpo.
$$
	[\varepsilon(\nu,T)d\nu]=\frac{E}{L^2 t}
$$
Definisco ulteriormente la funzione $\alpha(\nu,T)$, percentuale di assorbimento (percentuale di radiazione esterna che il corpo assorbe rispetto a quella incidente).
Sia $\alpha$ che $\varepsilon$ dipendono dal corpo in gioco.
Nel 1859 Kirchhoff riesce a dimostrare il seguente teorema:

________________________________________________________________________
Il rapporto $\frac{\varepsilon(\nu,T)}{\alpha(\nu,T)} \equiv I(\nu,T)$ è universale e non dipende dal corpo, se ciò non fosse vero violerei il principio termodinamico di Clausius.
________________________________________________________________________

Allora l'obiettivo diventa lo studio di $I(\nu,T)$, il che è particolarmente complesso perchè comporta la misura di 2 diverse quantità in contemporanea.
L'idea per fare ciò è quella di sfruttare un corpo nero, cioè un corpo che assorbe tutta la radiazione incidente e che ha dunque $\alpha(\nu,T)$ = 1, cioè $I(\nu,T)=\varepsilon(\nu,T)$. 
Posso costruire un corpo nero tramite un forno chiuso (in equilibrio termico), con una piccola apertura.
Il risultato sarà che la radiazione in ingresso verrà tutta assorbita per riflessioni parziali sulle pareti interne e quella emessa avrà distribuzione $I(\nu,T)$.

Su questo vengono condotti esperimenti dal 1860 al 1900. Le analisi teoriche classiche saranno tutte fallimentari.
La convenzione è quella di usare $\rho(\nu,T)$, densità di energia nella cavità, anzichè $\varepsilon(\nu,T)$. Cerchiamo il legame tra le 2, nel caso di corpo nero.
Parto da considerazioni dimensionali:
$$
	\begin{aligned}
	{}[\rho(\nu,T)d\nu]&=\frac{E}{L^3} \\
	[I(\nu,T)d\nu] &=\frac{E}{L^2 t} = \frac{L}{t} [\rho(\nu,T)d\nu]
	\end{aligned}
$$
$\frac{L}{t}$ è una velocità, l'unica velocità in gioco è $c$, dunque $I(\nu,T)=\#c\rho(\nu,T)$. (Nel caso di radiazione isotropa, altrimenti la costante moltiplicativa varierebbe con la posizione).

Calcoliamo il fattore moltiplicativo:
Considero un elemento di superficie $dA$ e calcolo l'energia che ci passa attraverso nel tempo $t$. Per farlo vado a considerare il contributo di tutti i $dV$ a distanza $r<ct$. 
Così facendo ottengo:

![[lezione1_1.png|411]]

$$ 
\begin{aligned}
\Delta E_{dA}(t) &= \int_{0}^{ct} dr \int \frac{d\Omega}{4\pi}\rho(\nu,T)dA \cos \theta \\
&= ct\rho(\nu,T)dA\int^1_{0} d\cos \theta \cos \theta \frac{ \int_{0}^{2\pi}d\phi}{4\pi}=\frac{c}{4}\rho\, dA\, t \equiv I(\nu,T)dA\,t
\end{aligned} 
$$
allora $\#=\frac{1}{4}$. Nell'integrale il fattore $\frac{1}{4\pi}$ è il fattore di normalizzazione dovuto all'isotropicità della radiazione. L'integrale sull'angolo solido è fatto solo per la semisfera "interna alla cavità".

Risultati delle analisi teoriche:
- 1879 Legge di Stefan-Boltzmann, di natura sostanzialmente empirica.
Definisce il potere emissivo del corpo nero: 
$$\mathcal{E}(T)=\int^\infty_{0} d\nu I(\nu,T) = \sigma T^4$$ con $\sigma \sim 5.69\cdot 10^-8 \, Wm^{-2}°K^{-4}$
- 1893 Legge di Wien, che trova origine in considerazioni termodinamiche
$$
	I(\nu,T)=a\nu^3f\left( \frac{\nu}{T} \right)
$$
andando ad analizzare i dati sperimentali ottiene:
$$
	I(\nu,T)=a\nu^3e^{-b \nu/T}
$$
La lagge di Wien ritrova S-B andando a integrare con un cambio di variabile $\frac{\nu}{T}=x$.
Inoltre ci fornisce quella che chiamiamo comunqemente legge di spostamento, infatti $f(x)$ è max per $x=x_{max}=\frac{\nu_{max}}{T}$ , allora $\nu_{max} \propto T$
Infine l'argomento dell'esponenziale dev'essere adimensionale, cioè esiste una costante $b$ tale $[b]=\frac{T}{\nu}$.
In analogia con la meccanica statistica, è ragonevole assumere l'esistenza di:
$$[k_{b}b]=b'=\frac{k_{b}T}{\nu}=\frac{E}{\nu}=Et$$
cioè una costante con le dimensioni dell'azione

#### Legge di Rayleigh-Jeans

L'idea adesso è di ricavare la densità $\rho(\nu,T)$ contenuta tra $\nu \text{ e }\nu+d\nu$ da principi primi.
Partiamo dalla seguente ipotesi:
- il corpo nero è una cavità in equilibrio termico con le pareti. Per il principio di sovrapposizione che emerge dalla linearità di Maxwell, ad ogni istante, posso vedere la radiazione interna come una sovrapposizione di onde stazionarie indipendenti, ciascuna con un modo di oscillazione diverso dalle altre. La densità di energia può dunque essere riscritta come: 
$$
	\rho(\nu,T) d\nu=n(\nu)d\nu \bar{E}(\nu,T)
$$
dove $n(\nu)$ è la densità volumica di modi di oscillazione delle onde stazionarie (che equivale al numero di onde stazionarie visto che oscillano tutte con modi diversi) e  $\bar{E}(\nu,T)$ è l'energia media trasportata da un'onda stazionaria di frequenza $\nu$ a temperatura $T$ (cioè l'energia media associata ad ogni modo di oscillazione).
Il calcolo di $n(\nu)$ ha natura puramente geometrica.

Partiamo dall'analisi dimensionale:

Sia $N(\nu)$ il numero di modi di oscillazione di frequenza $\nu$ nel volume $V \equiv L^3$. 
Dunque $[N(\nu)d\nu]=1\text{,}$ numero puro e necessariamente proporzionale a $L^3$.
L'unica forma possibile per $N(\nu)$ è $N(\nu) \propto L^3 \frac{\nu^2d\nu}{c^3}$.
Dunque $n(\nu)d\nu=\frac{1}{V} N(\nu)d\nu \propto \frac{\nu^2}{c^3}d\nu$.

Occupiamoci del calcolo della costante di proporzionalità. Considero una regione cubica del forno, la cui dimensione sia trascurabile rispetto al forno e tale che $L\gg \lambda$.

- Caso **1-D**
________________________________________________________________________
fisso arbitrariamente $L$ in modo che sia un multiplo intero della semilunghezza d'onda (cioè tale che contenga un numero intero di modi di oscillazione).
$$
	L=N \frac{\lambda}{2}=N \frac{c}{2\nu}
$$
da cui: 
$$
	N(\nu)=\frac{2\nu}{c}L \quad n(\nu)=\frac{2\nu}{c}
$$

- Caso **2-D**
________________________________________________________________________
passo ad un cubo bidimensionale e fisso nuovamente $L$.

![[Pasted image 20260922113034.png]]

$$
	AB'=\frac{\lambda}{2} \frac{1}{\cos \theta_{1}} \quad AB''=\frac{\lambda}{2} \frac{1}{\cos \theta_{2}}
$$
Poichè $\cos \theta_{1}$ e $\cos \theta_{2}$ sono i coseni direttori del vettore di propagazione dell'onda ho:
$$
	\cos^2\theta_{1}+\cos^2\theta_{2}=\cos^2\theta_{1}+\sin^2\theta_{1}=1
$$
Imponiamo che $L$ sia un multiplo sia di $AB'$ che di $AB''$.
$$
	L=n_{1} \frac{\lambda}{2} \frac{1}{\cos \theta_{1}} = n_{2} \frac{\lambda}{2} \frac{1}{\cos \theta_{2}}
$$
e abbiamo:
$$
	n_{1}=\frac{2L}{\lambda}\cos \theta_{1} \quad n_{2}=\frac{2L}{\lambda}\cos \theta_{2}
$$
e 
$$n_{1}^2+n_{2}^2=\frac{4L^2}{\lambda^2}=\frac{4\nu^2L^2}{c^2}$$
estendendo a d-dimensioni abbiamo, per gli stessi motivi di sopra: $\sum_{i=1}^d n_{i}^2=\frac{4\nu^2L^2}{c^2}$

- caso **3-D**
________________________________________________________________________
Mi concentro sul caso 3-D, dove l'equazione di prima diventa l'equazione della sfera:
$$
	n_{1}^2+n_{2}^2+n_{3}^2=\frac{4\nu^2L^2}{c^2}
$$
In particolare poichè $n_{1},n_{2},n_{3}>0$, stiamo descrivendo un ottante di sfera.
Quest'equazione mi va a descrivere una variazione continua dei 3 indici, cioè tutti i modi di oscillazione compatibili.
Sappiamo tuttavia che le uniche combinazioni di indici che ci interessano sono quelle in cui $n_{1},n_{2},n_{3}$ assumono tutti valori interi (tutti i modi con indici a valori non interi si eliminano a vicenda per interferenza distruttiva). 
Su un ottante di sfera questo' succede poco o mai.
Consideriamo dunque una corona sferica di spessore infinitesimo. A causa della differenza di scala tra $\lambda$ e $L$ avrò che questa corona sarà piena dei punti a coordinate intere.
![[Pasted image 20260922114430.png|]]
Alla fine, avrò che il numero di modi di oscillazione compatibili con la lunghezza $L$ di frequenza compresa tra $\nu$ e $\nu+d\nu$ è il numero di punti a coordinate intere che cadono nell'ottante positivo della corona sferica di $r=\frac{2\nu L}{c}$ e spessore $dr=\frac{2L}{c} d\nu$.
A causa della differenza di scale tra $\lambda$ e $L$ possiamo trascurare gli effetti di bordo e questa quantità sarà pari al volume della corona sferica.
$$
	N(\nu)d\nu=\frac{1}{8}4\pi\left( \frac{2\nu L}{c} \right)^2 \frac{2L}{c}d\nu =\frac{4\pi \nu^2}{c^3}L^3d\nu
$$
considerando che ogni onda stazionaria è un'onda elettromagnetica che ammette due polarizzazioni tra loro indipendenti (elettrica e magnetica), dobbiamo raddoppiare i modi di oscillazione e otteniamo:
$$
	\begin{aligned}
	N(\nu)d\nu&=\frac{8\pi \nu^2}{c^3}L^3 d\nu \\
	\Rightarrow n(\nu)d\nu&=\frac{8\pi \nu^2}{c^3}d\nu
	\end{aligned}
$$
E abbiamo ottenuto la densità volumica delle onde stazionarie.

Occupiamoci ora di trovare $\bar{E}(\nu,T)$. Da qua emergeranno tutti i problemi del caso.
- Dal teorema di equipartizione sappiamo che $<K> = \frac{1}{2}k_{B}T$
- Dal teorema del viriale sappiamo che $<K> = <V>$
Unendo le due otteniamo $\bar{E}=k_{B} T$
Andiamo a ricavare questo risultato in maniera esplicita.

Dall'elettromagnetismo sappiamo che:
$$
	E \propto \int dV(|\vec{E}|^2+|\vec{B}|^2)
$$
Tramite fourier è possibile riscrivere questo integrale come una somma infinita di contributi da oscillatori armonici di frequenza fisaata.
In particolare nelle onde classiche si ha che $I \propto |\vec{E}|^2$ **indipendentemente dalla frequenza di oscillazione** e troviamo dunque che per una certa frequenza fissata è possibile qualunque energia, semplicemente aumentando l'ampiezza dell'onda.

Facciamo ora alcune considerazioni di natura statistica, sappiamo della statistica di Boltzmann che la probabilità di trovare un'energia $E$ a una temperatura $T$ è proporzionale al fattore di Boltzmann.
$$
	P(E) \propto e^{-\beta T}=e^{-\frac{E}{kT}}
$$
calcoliamo l'energia media:
$$
	\bar{E}(\nu,T)=\frac{\int^\infty_{0} dE \, E e^{-\beta E}}{\int^\infty_{0}dE \,e^{-\beta E}} =-\frac{d}{d\beta}\left[ \ln \int^\infty_{0} dE \, e^{-\beta E} \right]=-\frac{d}{d\beta}\ln\left( \frac{1}{\beta} \right)=\frac{d}{d\beta}\ln \beta =\frac{1}{\beta}=k_{B}T
$$
che è proprio il risultato che ci aspettavamo.

Unendo tutto otteniamo:
$$
	\rho(\nu,T)d\nu=8\pi k_{B}T\frac{\nu^2}{c^3}d\nu \Rightarrow \tilde{\rho}(\lambda,T)=\frac{8\pi k_BT}{\lambda^4}d\lambda
$$
Questa forma è problematica infatti non mi riconduce a S-B, anzi, $\int^\infty_{0}\rho_{RJ}(\nu,T)d\nu$ non converge ad un valore finito, e abbiamo una violazione del principio di conservazione dell'energia.
Questo problema è noto come **catastrofe ultravioletta**.
Sfruttando soltanto principi della meccanica classica non è possibile risolvere questo problema.

Alla fine dell'800 abbiamo dunque 2 curve, Wien e RJ che fittano i dati sperimentali bene ma a frequenze diverse e non funzionano negli altri regimi, nasce quindi la necessità di interpolare le 2 curve.
![[Pasted image 20260922121459.png|419]]

#### Ipotesi di Planck

Nel 1900 Planck riesce dapprima a trovare un'interpolazione efficace, e successivamente a ricavarla, facendo però uso di ipotesi assurde per l'epoca:
- **Non tutte le energie sono possibili** per un onda E-M di frequenza $\nu$ fissata, bensì sono solo **multipli interi di un'energia fondamentale**, proporzionale alla frequenza.
$$
	E\to E_{n}=nE_{1}=nh\nu
$$
con $h=6.63 \, 10^{-34} \, Js$, costante fondamentale della natura con le dimensioni di un'azione.
Cambia dunque il modo in cui calcolo l'energia media.
$$
	\bar{E}=\frac{\sum_{n=0}^\infty E_{n}e^{-\beta E_{n}}}{\sum^\infty_{n=0}e^{-\beta n}} = -\frac{d}{d\beta}\ln\left[ \sum^\infty_{n=0}e^{-\beta E_{n}} \right]=-\frac{d}{d\beta}\ln \sum^\infty_{n=0}(e^{-\beta h\nu})^n
$$
otteniamo una serie geometrica che converge sempre perchè l'argomento è compreso tra 0 e 1, allora:
$$
	\bar{E}=-\frac{d}{d\beta}\ln\left[ \frac{1}{1-e^{-\beta h\nu}} \right]=\frac{d}{d\beta}\ln(1-e^{-\beta h \nu})=\frac{h\nu e^{-\beta h\nu}}{1-e^{-\beta h\nu}}=\frac{h\nu}{e^{-\beta h\nu}-1}
$$
Otteniamo così la formula di Planck:
$$
	\begin{aligned}
	\rho(\nu,T)d\nu&=\frac{8\pi \nu^2}{c^3} \frac{h\nu}{e^{h\nu/k_{B}T}-1}d\nu \\
	\tilde{\rho}(\lambda,T)d\lambda&=\frac{8\pi hc}{\lambda^3}\frac{1}{e^{hc/k_{B}T\lambda}-1}d\lambda
	\end{aligned}
$$
Verifichiamo che questa funzioni:
- per $\nu\to {0}$ devo ritrovare Rayleigh-Jeans, sviluppando con Taylor ho:
$$
	\rho(\nu,T) \sim \frac{8\pi \nu^3}{c^3} \frac{h}{1+\frac{h\nu}{k_{B}T}-1}=\frac{8\pi \nu^2}{c^3}k_{B}T
$$
- per $\nu\to \infty$ ho che $e^{h\nu/k_{B}T}\gg 1$ e $\rho(\nu,T) \sim \frac{8\pi}{c^3}h\nu^3 e^{-h\nu/k_{B}T}$ e ritrovo la legge di Wien
- Infine devo ritrovare la legge di Stefan-Boltzmann:
$$
	\begin{aligned}
	\mathcal{E} &= \int_{0}^\infty d\nu I(\nu,T)=\frac{c}{4}\int^\infty_{0}d\nu \rho(\nu,T)=A\int^\infty_{0}d\nu \, \frac{\nu^3}{e^{B\nu}-1} \\
		&=A \int^\infty_{0} d\nu\, \nu^3 \frac{e^{-B\nu}}{1-e^{-B\nu}}=A\int^\infty_{0} d\nu \, \nu^3 e^{-B\nu} \sum^\infty_{n=0}(e^{-B\nu})^n \\
		&=A\sum \int^\infty_{0} d\nu\,\nu^3 e^{-Bn\nu} =\frac{A}{B^4}\sum \frac{1}{n^4} \int^\infty_{0}dx \, x^3 e^{-x}\\
		&=\frac{6A}{B^4} \zeta(4)=\frac{6A}{B^4} \frac{\pi^4}{90}\equiv \sigma T^4
	\end{aligned}
$$
dove negli ultimi passaggi abbiamo fatto uso della funzione Gamma di Eulero e Zeta di Riemann e abbiamo posto $A=\frac{8\pi h}{c^3} \frac{c}{4}$ e $B=\frac{\nu}{k_{B}T}$.
Così facendo si ottiene:
$$
	\sigma=\frac{2}{15}\pi^5 \frac{k_{B}^4}{h^3 c^2}\sim {5}.67 \cdot 10^{-8} Wm^{-2}°K^{-4}
$$

Per un po' si era convinti che questa quantizzazione provenisse dalla proprietà della materia che emetteva la radiazione, finchè nel 1905 Einstein non spiegò l'effetto fotoelettrico tramite l'ipotesi che la quantizzazione fosse propria delle radiazioni elettromagnetiche.

### Effetto Fotoelettrico

L'effetto fotoelettrico è un esperimento in cui una lastra di metallo viene colpita da un fascio di luce monocromatica e si osservano i seguenti effetti:
1. la lastra **può** emettere $e^-$
2. **se** c'è emissione, il numero di elettroni emessi è proporzionale all'intensità della luce incidente
3. al di sotto di una frequenza critica $\nu_{0}$, che dipende dal metallo, **NON** c'è emissione, indipendentemente dall'intensità
4. l'emissione è "istantanea"
5. la massima energia cinetica trasportata dagli elettroni usciti dipende dal metallo ma **NON** dall'intensità della luce
I primi 2 effetti sono ragionevoli anche da un punto di vista classico, gli altri effetti no. Per spiegarli Einstein sfrutta l'idea dei pacchetti di energia di Planck e formula le seguenti ipotesi:
- gli $e^-$ sono legati al metallo da un potenziale di ionizzazione $V_{0}$
- la radiazione viene assorbita dal metallo in pacchetti di energia $E=h\nu$
- c'è emissione solo se $h\nu-V_{0}>0$, allora la frequenza $\nu_{0}=\frac{V_{0}}{h}$ non dipende dall'intensità.
- l'energia cinetica massima è data $K_{max}=h\nu-V_{0}$ . Elettroni energeticamente più alti sono pressochè impossibili e prevedono che lo stesso elettrone venga colpito consecutivamente da più di un fotone.

#### Effetto Compton

L'effetto Compton descrive il processo d'urto tra un $e^-$ e della radiazione elettromagnetica (raggi x). Anche in questo caso sorgono dei problemi nella descrizione classica del fenomeno ed è necessario andare ad introdurre una quantizzazione.

![[Pasted image 20260924141007.png]]

Per risolvere il problema classicamente, vado a risolvere le equazioni di Maxwell con opportune condizioni al contorno. Così facendo trovo che $\lambda$ della radiazione non cambia dopo l'urto ed è indipendente dall'angolo $\theta$. Tuttavia entrambe queste affermazioni sono in disaccordo con i risultati sperimentali.

Introduciamo dunque la quantizzazione e immaginiamo l'onda come se fosse fatta di tanti pacchetti (quantizzati) dotati di un'energia e un impulso (i fotoni).
Adesso modelliamo l'urto come un urto tra particelle relativistiche.

![[Pasted image 20260924141326.png]]

scriviamo il quadrimpulso delle particelle:
$$p^\mu=\left( \frac{E}{c}, \vec{p} \right)$$.
Sappiamo che l'energia del fotone è $E_{\gamma}=h\nu$ e la sua massa è $m_{\gamma}=0$. Applicando mass-shell si trova:
$$
	(h\nu)^2=|\vec{p}|^2 c^2 \Rightarrow |\vec{p}|=\frac{h\nu}{c}=\frac{h}{\lambda}
$$
cioè anche l'impulso del fotone è quantizzato.
Per l'elettrone ho invece:
$$
	E_{e}=\sqrt{ |p_{e}|^2c^2+m_{e}^2c^2 }
$$
Studiamo l'urto imponendo la conservazione del quadrimpulso:
$$
	\begin{cases}
	E_{\gamma}+E_{e}= E'_{\gamma}+E'_{e} \\ \\
	\vec{p}_{\gamma}+\vec{p}_{e}=\vec{p}'_{\gamma}+\vec{p}'_{e}
	\end{cases}
$$
scelgo il sistema a targhetta fissa in cui l'elettrone è a riposo.
$$
	\begin{cases}
	E_{\gamma}+m_{e}c^2=E_{\gamma}'+E_{e}' \\
	\vec{p}_{\gamma}=\vec{p}'_{\gamma}+\vec{p}'_{e}
	\end{cases}
$$
$$
\begin{aligned}
	E_{\gamma}-E'_{\gamma}+m_{e}c^2&=E_{e}' = \sqrt{ m_{e}^2c^4+|\vec{p}_{e}|^2 c^2 }=\sqrt{ m_{e}c^4+|\vec{p}_{\gamma}-\vec{p}_{\gamma}'|^2c^2 } \\
	&=\sqrt{ m_{e}^2 c^4+|\vec{p}_{\gamma}|^2 c^2+|\vec{p}'_{\gamma}|c^2-2|\vec{p}_{\gamma}||\vec{p}_{\gamma}'|\cos^2\theta c^2 }\\
	&=\sqrt{ m_{e}^2c^2 +E_{\gamma}^2+E'^2_{\gamma}-2E_{\gamma}E'_{\gamma}\cos \theta c^2}
\end{aligned}
$$
elevo tutto al quadrato:
$$
	(E_{\gamma}+E'_{\gamma}+m_{e}c^2)^2= m_{e}^2c^2 +E_{\gamma}^2+E'^2_{\gamma}-2E_{\gamma}E'_{\gamma}\cos \theta c^2
$$
andando a sviluppare il quadrato a sinistra e semplificando otteniamo:
$$
	m_{e}c^2(E_{\gamma}-E_{\gamma}')-E_{\gamma}E'_{\gamma}=-E_{\gamma}E_{\gamma}'\cos \theta
$$
andando a sostituire $E=h\nu$:
$$
	\begin{aligned}
	m_{e}c^2\left( \frac{hc}{\lambda}-\frac{hc}{\lambda'} \right)-\frac{h^2c^2}{\lambda \lambda'}&=-\frac{h^2c^2}{\lambda \lambda'}\cos \theta \\
	\Rightarrow \lambda'-\lambda&=\frac{h}{m_{e}c}(1-\cos \theta)
	\end{aligned}
$$
Abbiamo ottenuto la formula dell'effetto Compton, che contraddice totalmente i calcoli classici in quanto $\lambda'$ non solo differisce da $\lambda$ ma varia anche con $\theta$.

Questa formula ci permette anche di introdurre la lunghezza d'onda Compton (dell'elettrone):
$$
	\lambda_{c}=\frac{h}{m_{e}c}
$$
che equivale alla lunghezza d'onda di un fotone che ha come energia l'energia a riposo dell'$e^-$.
Analogamente posso definire la lunghezza d'onda Compton di varie particelle differenti.

#### Spettroscopia e modelli atomici.

Ancora una volta partiamo da osservazioni sperimentali difficili da spiegare con la fisica classica, in particolare osserviamo che:
- una scarica elettrica in un gas produce radiazione elettromagnetica con uno **spettro discreto**, lo spettro di emissione
- un gas illuminato da una luce generica assorbe luce solo alle stesse lunghezze d'onda del proprio spettro di emissione.
![[Pasted image 20260924143813.png]]

Con esperimenti più precisi si arriva ad osservare che ogni riga è in realtà un multipletto di righe molto fitte, questo porterà allo studio della struttura fine dell'atomo.
Comparando i pattern di emissione di varie sostanze diverse emerge un pattern, descritto dalla formula di Rydberg:
$$
	\frac{1}{\lambda}=R\left( \frac{1}{n_{1}^2}-\frac{1}{n_{2}^2} \right) \text{ con } n_{2}>n_{1} \in\mathbb{N}
$$
$R$ si dice costante di Rydberg. Fissando $n_{1}$ e variando gli altri numeri posso studiare la distanza tra le righe, ottengo così serie che prendono nomi diversi:
- $n_{1}=1, \, n_{2}=2,3,\dots$ prende il nome di Serie di Lyman
- $n_{1}=2, \, n_{2}=3,4,\dots$ prende il nome di Serie di Balmer
- $n_{1}=3, \, n_{2}=4,5,\dots$ prende il nome di Serie di Ritz
Tuttavia non si riesce a spiegare l'origine di questa formula, pertanto nasce la necessità (intorno agli anni '10 del 1900) di studiare dei modelli atomici coerenti che spieghino questa formula.
Come il corpo nero, questo problema affronta l'interazione tra materia e radiazione.

Con la scoperta dell'elettrone (Thomson), si scopre che l'atomo si può "rompere".
L'elettrone è carico negativamente ma sappiamo che la materia è neutra dunque l'atomo dev'essere in parte carico positivamente e contenere degli elettroni.
Per questa ragione Thomson formula il modello "plum-pudding" ipotizzando l'atomo come una sfera carica piena, di densità di carica positiva contenente elettroni "incastrati". All'epoca questo è l'unico modello plausibile, infatti le equazioni di Maxwell escludono il modello planetario, l'elettrone emettendo radiazioni perderebbe energia, cadendo nel nucleo in $10^{-11} s$.

![[Pasted image 20260924150440.png|700]]

Nel 1911 Rutherford elabora un esperimento per verificare il modello di Thomson.
Una lastra d'oro viene bombardata di particelle $\alpha$, cariche positivamente e si studiano le deviazioni di questa particella su di un rivelatore. Ci si aspetta molte piccole deviazioni ma ciò che si osserva sono poche deviazioni di entità molto elevata. Questo porta alla riemersa del modello planetario.
![[Pasted image 20260924150706.png]]

Rutherford riesce anche a calcolare la densità di carica del nucleo positivo, $\rho_{nucleo} \sim 10^{11} kg/cm^3$,  quindi il nucleo è estremamente concentrato. 
$$
	\frac{r_{atomo}}{r_{nucleo}}\sim 10^5
$$
Dunque la materia è prevalentemente vuota.
Resta però aperto il problema legato al collasso dell'elettrone nel nucleo.

Nel 1913 Bohr propone una soluzione tramite le seguenti ipotesi:
- $\exists$ "stati stazionari", orbite privilegiate alle quali gli $e^-$ sono vincolati e dalle quali **NON irradiano**. La radiazione viene emessa/assorbita soltanto al passaggio da un'orbita all'altra.
- 
Bohr fornisce anche una regola di selezione per queste orbite.
Imponiamo che l'integrale di linea del moto dell'elettrone sulle orbite periodiche sia quantizzato. Questo integrale ha dimensioni di un'azione e ci porta all'introduzione del *quanto d'azione*.
$$
	\oint p_{i}dq_{i} = n_{i}h
$$
Studiamo il caso semplificato di orbite circolari. D'ora in poi useremo sempre unità Gaussiane.

![[Pasted image 20260924151513.png]]

Il potenziale coulombiano è: $-Z \frac{e^2}{r}$
$$
	\begin{aligned}
	|\vec{v}|&=\text{cost}\\
	|\vec{r}|&=\text{cost}=r \\
	dq&=r d\phi\\
	\oint pdq &=2\pi pr=2\pi mvr=2\pi L_{z}
	\end{aligned}
$$
cioè:
$$
	L_{z}=\frac{n_{i}}{2\pi} h=n_{i}\hbar
$$
Cioè il momento angolare è quantizzato.

**Oss:** il momento angolare è quantizzato in una sola componente (che dipende dalla mia scelta di assi) e questo diventa problematico quando vado a ruotare il mio sistema è il momento totale va ad ammettere anche altre componenti non quantizzate. Vedremo poi che significato ha questo.

Studiamo ora l'energia di queste orbite.
$$
	E\to E_{n} = \frac{1}{2}mv_{n}^2-\frac{Ze^2}{n}
$$
Per il secondo princio della dinamica, essendo l'accelerazione solo centripeta, la forza elettrostatica agente sulla particella è centripeta:
$$
	\frac{mv^2_{n}}{r_{n}}=\frac{Ze^2}{r_{n}^2}
$$
dunque:
$$
	\begin{aligned}
	mv^2_{n}=\frac{Ze^2}{r_{n}} \quad \Rightarrow E_{n} = -\frac{1}{2} \frac{Ze^2}{r_{n}}
	\end{aligned}
$$
Riprendiamo il quanto d'azione:
$$
	mv_{n}r_{n}=n\hbar \quad \Rightarrow v_{n}=\frac{n\hbar}{mr_{n}}
$$
da cui:
$$
	m \frac{n^2\hbar^2}{m^2 r_{n}^2}=\frac{Ze^2}{r_{n}} \to r_{n}=\frac{\hbar^2}{mZe^2}n^2
$$
e:
___
$$
	E_{n}=-\frac{1}{2} \frac{mZ^2e^4}{2\hbar^2} \frac{1}{n^2}
$$
___

Questa formula per trovare i livelli energetici degli orbitali "privilegiati" è esatta e verrà ristrovata dall'equazione di Schrödinger.
Inoltre ritrova efficacemente la formula di Rydberg andando a fare:
$$
	\nu_{n_{1}n_{2}}=\frac{c}{\lambda_{n_{1}n_{2}}}=\frac{E_{n_{1}}-E_{n_{2}}}{h}
$$
Così facendo Bohr predice anche efficacemente il valore della costante di Rydberg dell'idrogeno:
$$
	R_{H}=\frac{me^4}{4\pi \hbar^3 c}
$$

#### Notazioni utili allo sviluppo della teoria

Introduciamo ora alcune notazioni che torneranno utili nello sviluppo della teoria.

- Raggio di Bohr: $$r_{1}=a_{0}=\frac{\hbar^2}{me^2}\simeq 0,053\,nm$$
- Costante di struttura fine (adimensionale, qua sotto espressa in unità Gaussiane): 
$$
	\alpha=\frac{e^2}{\hbar c}\simeq \frac{1}{137}
$$
- Lunghezza d'onda compton dell'elettrone: $$\lambda_{c}=\frac{h}{m_{e}c}\simeq 2.4\cdot 10^{-12}m$$
- Equivalente energetico della massa dell'elettrone: $m_{e}c^2\simeq 0.511 \, MeV$
- Raggio, ed energia dell'n-simo orbitale:
$$
	\begin{aligned}
	r_{n}&=a_{0}n^2 \\
	E_{n}&=-\frac{e^2}{2a_{0}} \frac{1}{n^2} \\
	E_{1}&=-\frac{e^2}{2a_{0}}=-\frac{me^4}{2\hbar^2}=-\frac{\alpha^2}{2} mc^2\simeq -13.6 \, eV
	\end{aligned}
$$
- Costante di Rydberg: 
$$R=\frac{\alpha}{4\pi a_{0}}$$

## Domande per revisione
- [ ] Quali sono i tentativi classici di soluzione al problema della radiazione del corpo nero?
- [ ] Quali sono i problemi della legge di Wien e di quella di Rayleigh-Jeans? Come risolve il problema Planck?
- [ ] Come posso applicare l'ipotesi di Planck all'effetto fotoelettrico?
- [ ] Come posso applicare la stessa ipotesi all'effetto Compton?
- [ ] Come Bohr riesce a spiegare gli spettri di emissione dell'idrogeno e la formula di Rydberg?
- [ ] Quanto valgono il raggio di Bohr, la costante di struttura fine, l'equivalente energetico della massa dell'elettrone e l'energia del primo orbitale dell'idrogeno?
## Collegamenti
- Lezione precedente: [[]]
- Concetti collegati: [[]]

