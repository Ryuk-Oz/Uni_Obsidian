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

#### Notazioni e numeri utili

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
- Costante di Rydberg dell'idrogeno: 
$$R_{H}=\frac{\alpha}{4\pi a_{0}}$$

Vediamo adesso la verifica sperimentale della quantizzazione del momento angolare.


**Lezione associata:** [[1.Introduzione storica alla meccanica quantistica]]