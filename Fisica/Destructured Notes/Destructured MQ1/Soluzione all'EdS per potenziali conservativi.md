
Ci concentriamo come sempre su un problema semplificato per provare a trovare una soluzione dell'equazione di Shrödinger. Consideriamo sistemi conservativi, cioè sistemi per i quali il potenziale è indipendente dal tempo. Per sistemi di questo tipo l'Hamiltoniana si conserva ed è:
$$
	H=\frac{|\vec{p}|^2}{2m}+V(\vec{r})\quad \text{(per una particella)}
$$
Nel caso in cui il sistema fosse fatto da più particelle avremmo:
$$
	H=\sum_{i=1}^n \frac{|\vec{p}_{i}|^2}{2m_{i}}+V(\vec{r}_{1},\vec{r}_{2},\dots,\vec{r}_{n})
$$
Essendo il sistema conservativo abbiamo $H(\vec{p},\vec{r})=E=\text{cost}$ 
**Achtung!** Non ho completamente rimosso la dipendenza dal tempo. Resta una dipendenza temporale implicita contenuta in $\vec{p}=\vec{p}(t)$ e $\vec{r}=\vec{r}(t)$.

Proviamo a risolvere l'equazione in queste condizioni.
$$
	i\hbar \frac{ \partial \psi }{ \partial x } =-\frac{\hbar^2}{2m}\Delta \psi+V(\vec{r})\psi
$$
L'equazione così scritta (senza dipendenza temporale esplicita) è invariante per traslazioni temporali, per questo possiamo risolverla per separazione di variabili, andando a cercare una soluzione in forma fattorizzata.
$$
	\psi(\vec{r},t)=u(\vec{r})f(t)
$$
Se riesco ulteriormente a dimostrare che soluzioni di questo tipo formano una base di $L^2(\mathbb{R}^3)$, ho trovato tutte le soluzioni possibili.
Sostituiamo il nostro Ansatz nell'equazione.
$$
	\frac{ \partial \psi }{ \partial t } =u(\vec{r})\frac{ d f }{ d t } \qquad \Delta \psi=f(t)\Delta u(\vec{r}) 
$$
$$
	\longrightarrow \, i\hbar u(\vec{r})\frac{df}{dt}=-\frac{\hbar^2}{2m}f(t)\Delta u(\vec{r})+V(\vec{r})u(\vec{r})f(t)
$$
Spostiamo la tutte le dipendenze da $\vec{r}$ da un lato e quelle da $t$ da un'altro. 
Per farlo dividiamo l'equazione per $\psi$. Questo potrebbe apparentemente causare problemi perchè in alcuni punti la funzione d'onda si annula. Per questo andiamo a fare quest'operazioni in tutti i punti dove $\psi\neq 0$ e dove si annula la estendiamo per continuità. Otteniamo:
$$
	\frac{i\hbar}{f(t)} \frac{df}{dt}=-\frac{\hbar^2}{2m} \frac{\Delta u(\vec{r})}{u(\vec{r})}+V(\vec{r})\overset{!}{=} E
$$
Spieghiamo quest'uguaglianza. I due membri devono essere tra loro uguali ma dipendono da variabili diverse tra loro scorrelate. Per questo motivo devono essere entrambe uguali ad una stessa costante. Inoltre entrambi i membri hanno dimensione di un'energia. Per questo motivo chiamiamo questa costante $E$.

Risolviamo separatamente entrambi i membri dell'equazione.
Il primo membro è banale: 
$$
	\frac{i\hbar}{f(t)}df=Edt \to \frac{df}{f}=-\frac{i}{\hbar}Edt\implies f=f(0)e^{ -\frac{i}{\hbar}Et }
$$
$f(0)$ è una costante fissata tramite la normalizzazione.
Si tratta di un fattore universale, presente in tutte le soluzioni con potenziali conservativi, indipendentemente dalla forma funzionale del potenziale.

Studiamo l'altro membro:

>[!summary] Equazione di Shrödinger stazionaria
>
>$$
>	-\frac{\hbar^2}{2m}\Delta u(\vec{r})+V(\vec{r})u(\vec{r})=Eu(\vec{r})
>$$

A differenza dell'altro membro, questo dipende dal potenziale $V$

**OSS:** se scelgo $u(\vec{r})$ reale questa è un'equazione reale.
**OSS:** non sempre tutti i valori di $E$ sono compatibili con quest'equazione, la condizione di normalizzabilità determina i valori di $E$ compatibili, che possono comparire in uno spettro discreto o continuo

##### Studio delle soluzioni fattorizzate

Presa una soluzione $u_{E}(\vec{r})$ dell'equazione stazionaria, la soluzione dell'equazione completa è:
$$
	\psi_{E}(\vec{r},t)=u_{E}(\vec{r})e^{ -(i/\hbar)Et }
$$
Soluzioni di questo tipo prendono il nome di funzioni d'onda degli **stati stazionari**. Occupiamoci di alcune proprietà di questa classe di soluzioni.

1. Sono soluzioni stazionarie, ovvero non variano nel tempo. Il motivo è che le uniche osservabili che andiamo a misurare non sono le funzioni d'onda, bensì le densità di probabilità di posizione. 
$$
   	\rho_{E}(\vec{r},t)=|u_{E}(\vec{r})e^{ -Ct }|=|u_{E}(\vec{r})|
   $$
   dipende solo dalla posizione e non dal tempo.
   
2. Possiamo interpretare gli stati stazionari come soluzioni di definita energia $E$. 
   Iniziamo riscrivendo l'equazione tramite gli operatori
$$
   	\begin{aligned}
	x&\to \hat{x}=x \cdot \\
	p&\to \hat{p}=-i\hbar \frac{ \partial  }{ \partial x } \\
	H&\to \hat{H}=\frac{|\hat{p}|^2}{2m}+V(\hat{\vec{r}})=-\frac{\hbar^2}{2m}\Delta + V(\vec{r})
	\end{aligned}
   $$
   Dunque possiamo riscrivere l'equazione stazionaria come: 
$$
	\hat{H}u(\vec{r})=Eu(\vec{r})
   $$
   cioè $u(\vec{r})$ è autofunzione dell'operatore $\hat{H}$ agli autovalori $E$.
   Se adesso andiamo a calcolare il valore medio $<H>_{\psi_{E}}$ troviamo:    
$$
	<H>_{\psi_{E}} \equiv \int d^3r \, \psi^*_{E}(\vec{r},t)\hat{H}\psi_{E}(\vec{r},t)=\int d^3r\, u^*_{E}\hat{H}u_{E}=E\int d^3r\,|u_{E}(\vec{r})|^2=E
   $$
   Nell'ultimo passaggio abbiamo sfruttato la normalizzazione.
   Abbiamo trovato che il valore medio dell'energia non dipende dal tempo (conseguenza del teorema di Ehrenfest, il valore medio continua a seguire la legge classica di conservazione dell'energia).
   Si dimostra molto rapidamente in modo analogo che $<H^2>_{\psi_{E}}=E^2$.
   Dunque $\Delta H_{\psi_{E}}= <H^2>-<H>^2=0$ e NON ho INDETERMINAZIONE sull'energia. L'energia di ogni stato è dunque ben definita.
   
3. La soluzione generale dell'edS per sistemi conservativi è la combinazione lineare degli stati stazionari. La soluzione dell'equazione stazionaria ci da lo spettro delle possibili energie, che può essere discreto o continuo. 
   Nel caso discreto oteniamo la soluzione generale come:
$$
	\psi(\vec{r},t)\equiv \sum_{n}c_{n}u_{n}(\vec{r})e^{ -\frac{i}{\hbar}E_{n}t }
$$
   Nel caso continuo:
   $$
	\psi(\vec{r},t)\equiv \int dE \, c(E) u_{E}(\vec{r})e^{ -\frac{i}{\hbar}Et }
   $$
4. Le soluzioni suggeriscono un'interpretazione probabilistica anche per l'equazione in presenza di potenziale. Sostituendo $E=\hbar \omega$ (energia della particella libera) nella soluzione continua otteniamo $\int\dots e^{ -i\omega t }$ che posso riscrivere come TF e trovare l'interpretazione probabilistica.
   Dunque possiamo concludere che questo caso sia una "generalizzazione" della particella libera.
   Nel caso discreto andiamo ad interpretare $|C_{n}|^2$ come la probabilità di trovare il livello energetico $E_{n}$ facendo una misura di $E$ sul sistema descritto da $\psi$. Analogamente nel caso continuo possiamo interpretare $|c(E)|^2$ come la densità di probabilità dell'osservabile energetica $E$.
   In accordo con questa interpretazione, devono valere alcune relazioni di consistenza:
$$
	\begin{aligned}
	\text{se } ||\psi||&=1 \implies \sum_{n}|c_{n}|^2=1;\quad \text{"simil-equazione di Parseval"}\\
	<H>_{\psi} &\equiv \int d^3r\,\psi^*\hat{H}\psi = \sum |c_{n}|E_{n}
	\end{aligned}
$$

5. La combinazione lineare di stati stazionari non è stazionaria.
$$
\begin{aligned}
\psi(\vec{r},t)&=c_{1}u_{1}(\vec{r})\exp\left[ -\frac{i}{\hbar}E_{1}t \right]+c_{2}u_{2}(\vec{r})\exp\left[ -\frac{i}{\hbar}E_{2}t \right]\\
\implies \rho(\vec{r},t)&=|\psi(\vec{r},t)|^2 =|c_{1}|^2|u_{1}(\vec{r})|^2+|c_{2}|^2|u_{2}(\vec{r})|^2+2\mathrm{Re}\left[ c_{1}^*c_{2}u_{1}^*u_{2}\exp\left( -\frac{i}{\hbar}(E_{2}-E_{1})t \right) \right]
\end{aligned}
$$
   La densità di probabilità di posizione oscilla con frequenza angolare $\omega_{ij}=\frac{E_{i}-E_{j}}{\hbar}$. Da qua si ritrova la formula di Rydberg.

6. L'interpretazione fisica di $E$ come energia, richiede $E\in \mathbb{R}$. Siccome $E$ è autovalore di $\hat{H}$, questo va ad imporre una condizione su $\hat{H}$ (che vedremo essere l'ermeticità). Se $E$ fosse complessa, comparirebbe un termine esponenziale reale che non scompare nella densità di probabilità di posizione. La probabilità andrebbe a diminuire nel tempo e la soluzione non risulterebbe essere stazionaria.


**Lezione Associata:** [[2.Equazione di Shrödinger]]