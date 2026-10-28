
Il moto browniano prende il nome da Brown (biologo) che osserva al microscopio il polline in sospensione nell'acqua e vede che non sta fermo, bensì si muove casualmente.
Brown si chiede il perchè e si mette a osservare molti materiali diversi e concluede che il moto NON ha origine biologica.
Faraday e Cantoni ripetono questi esperimenti e ipotizzano che il moto Browniano possa causare il calore.
Un fisico francese (non so chi) riesce a legarlo alla temperatura.
Nel 1905 Einstein fornisce un Hp per spiegarlo: il polline in acqua è soggetto all'urto da parte di molecole di acqua e causa il moto del polline.
Einstein era interessato a dare una dimostrazione empirica della meccanica statistica e ci riesce, noi faremo dei calcoli più semplici di quelli di Einstein, quelli di Langevin.
Infine Perrin sulla base del lavoro di Einstein fa degli esperimenti quantitativi che gli vincono il nobel.

#### Approccio di Langevin (1908)

L'idea di Langevin è che l'equazione del moto sia soggetta  a 2 forze:
$$
	m\ddot{x}=\underbrace{-6\pi a\nu \dot{x}}_{\text{Forza di Stokes}}+\underbrace{z(t)}_{\text{urti molecolari}}
$$
Abbiamo dunque una forza deterministica macroscopica combinata con una forza microscopica casuale.
$z$ è una variabile aletaoria scorrelata in $x$ con $\langle z \rangle=0$. (Per molti urti lo spostamento causato dagli urti è nullo).
Definiamo tempo di rilassamento il tempo che impiega il grano a fermarsi (nel caso di assenza di urti molecolari, $z=0$).
Calcoliamo il tempo di rilassamento:
$$
	m\dot{v}=-6\pi a\nu v\to v(t)=v(0)e^{ -t/\tau }\implies \tau=\frac{m}{6\pi a\nu}\simeq 10^{-7} \quad \text{tempo di rilassamento}
$$
Il tempo caratteristico di un urto (cioè il tempo che passa tra 2 urti successivi), che equivale al tempo di correlazione di $z(t)$ è $\sim 10^{-11}s$, trascurabile rispetto al tempo di rilassamento.

Per risolvere l'equazione dobbiamo riuscire a scrivere la forma del rumore. L'idea di Langevin è quella di moltiplicare per $x$. 
$$
	mx \ddot{x}=-6\pi a\nu x \dot{x}+xz
$$
Ora vado a mediare su di un tempo molto più piccolo del tempo di rilassamento $\ll \tau$ ma molto più grande del tempo caratteristico di urto $\gg{10}^{-11}s$.
$$
	m\langle x \ddot{x} \rangle = -6\pi a\nu \langle x \dot{x} \rangle +\langle xz \rangle 
$$
L'idea è che per tempi $\gg 10^{-11}s$ e urti scorrelati nelle posizioni: $\langle xz \rangle=\langle x \rangle\langle z \rangle=0$ .
Dunque possiamo riscrivere l'equazione come:
$$
	\frac{1}{2} \frac{d^2}{dt^2} \langle x^2 \rangle - \langle \left( \frac{dx}{dt} \right)^2 \rangle =-\frac{6\pi a\nu}{m} \frac{1}{2} \frac{d}{dt} \langle x^2 \rangle 
$$
A questo punto aggiungiamo un ulteriore ipotesi, cioè che il  grano sia in equilibrio termico $\implies \frac{1}{2} mv^2=\frac{1}{2} kT$.
Sotto queste ipotesi:
$$
	\langle \left( \frac{dx}{dt} \right)^2 \rangle =\frac{k}{m}T \quad \text{per } m\gg 1 \quad \langle  \left( \frac{dx}{dt} \right)^2\rangle\to 0 
$$
Per grani grandi la velocità media al quadrato tende a 0.
E possiamo riscrivere l'equazione nel seguente modo:
$$
\begin{aligned}
\frac{1}{2} \frac{d^2}{dt^2} \langle x^2 \rangle &=\frac{kT}{m} -\frac{6\pi a\nu}{m} \frac{1}{2} \frac{d}{dt} \langle x^2 \rangle \\
&=\frac{kT}{m} - \frac{1}{2\tau} \frac{d}{dt} \langle x^2 \rangle 
\end{aligned}
$$
Risolvendo con condizione iniziale $x(0)=0$ troviamo:
$$
	\langle x^2(t) \rangle =\frac{2kT}{m}\tau^2 \left[ \frac{t}{\tau}-(1-e^{ -t/\tau }) \right]
$$
Studiamo i limiti di questa soluzione per tempi brevi:
- se $\frac{t}{\tau}\ll 1$ trovo:
$$
	\langle x^2(t) \rangle =\frac{2kT}{m} \tau^2 \left[ \frac{t}{\tau}-1+1-\frac{t}{\tau}+\frac{1}{2} \left( \frac{t}{\tau} \right)^2+\dots \right]=\frac{kT}{m} t^2 =\langle v^2 \rangle t^2
$$
  Vedo la particella che si muove di moto rettilineo uniforme per tempi molto brevi
E per tempi lunghi:
- se $t\gg \tau$ trovo:
 $$
	\langle x^2(t) \rangle \simeq\frac{2kT}{m} \tau^2 \left[ \frac{t}{\tau}-1 \right] \simeq\left( \frac{2kT}{m}\tau \right)t\equiv 2Dt \qquad \text{moto diffusivo}
 $$
 $D$ prende il nome di coefficiente di diffusione: $D=\frac{kT}{6\pi a\nu}$, risultato analogo a quello trovato da Einstein.
 Questo risultato è indipendenta dalla statistica di $z$. In realtà in molti processi stocastici il moto è DIPENDENTE dalla statistica.


**Lezione Associata:** [[5. Moto Browniano e Random Walk]]