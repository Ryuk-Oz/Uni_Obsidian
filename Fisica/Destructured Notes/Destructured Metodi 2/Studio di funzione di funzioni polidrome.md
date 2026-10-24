Occupiamoci per prima cosa dello studio dei punti di diramazione, per poi spostarci sullo studio dell'analiticità e della polidromia.
##### Studio dei punti di diramazione

Abbiamo visto durante l'esempio della radice quadrata che i punti da cui partono i tagli di ciascun foglio si chiamano punti di diramazione e anche spostando il taglio i punti di diramazione restano gli stessi.
Nel caso del $\log z$ i punti di diramazione sono $0$ e $\infty$.
In un singolo foglio i punti di diramazione sono sempre singolarità non isolate, infatti preso qualunque intorno del punto di diramazione andrò inevitabilmente ad includere parte del taglio. Pertanto non è possibile sviluppare una funzione polidroma attorno a un punto di diramazione.
Sulla superficie di Riemann i punti di diramazione sono invece singolarità che si estendono su ogni piano (li studieremo meglio nelle lezioni successive, spero).

Come posso verificare che $z_{0}$ sia un punto di diramazione per una certa $f(z)$? 
L'idea è quella di procedere per costruzione. Prendo il mio punto sospetto $z_{0}$ e studio $f(z)$ in un intorno $I_{\delta}(z_{0})$.
All'atto pratico studi $f$ in un punto $z$ a distanza fissa da $z_{0}$ e compio un giro in senso antiorario.
![[Pasted image 20260930165010.png|278]]

se dopo un giro la funzione $f(z)$ è tornata al valore di partenza $\implies$ $z_{0}$ NON è un punto di diramazione. Se invece $f(z)$ non torna mai al valore di partenza o ci torna dopo un certo numero di giri $\implies$ $z_{0}$ è un punto di diramazione.
Ulteriormente $f(z)$ non ritorna mai al suo valore originale allora si dice che $f(z)$ è una funzione polidroma con polidromia di ordine $\infty$.
Se invece torna al valore iniziale dopo $n$ giri, diciamo che la funzione ha polidromia di ordine $n-1$.
Ad esempio $\log z$ ha polidromia di ordine $\infty$ mentre $\sqrt{ z }$ ha polidromia di ordine 1.

Vediamo come farlo su di un esercizio.
- **Esercizio:**
$$
	\log\left( \frac{{z-a}}{z-b} \right) \quad a,b \in \mathbb{C}
$$
ho diversi modi di fare ciò che ho appena descritto.

1. Mi riconduco ad un caso noto con un cambio di variabile. Pongo: 
$$
   	w=\frac{{z-a}}{z-b}
   $$
Trasformazione che manda $\bar{\mathbb{C}}\to \bar{\mathbb{C}}$. 
Ottengo $\log w$ con $w \in \mathbb{C}$, ma conosco già i punti di diramazione della funzione logaritmo: $w=0$ e $w=\infty$ . Con la trasformazione inversa ottengo che $z=a$ e $z=b$ sono i punti di diramazione e il taglio va da $a$ a $b$.

2. Applico alla lettera l'approccio costruttivo.
Identifico $z=a$ come punto sospetto, allora giro attorno a $z=a$.
$$\begin{aligned}
\log\left( \frac{{z-a}}{z-b} \right)&=\log | \frac{z-a}{z-b}|+iarg\left( \frac{{z-a}}{z-b} \right)+i 2\pi n \\
&=\log | \frac{z-a}{z-b}|+i(\varphi_{a}-\varphi_{b})+i{2}\pi n
\end{aligned}
$$
Facendo un giro intorno ad $a$ osserviamo che:
$$
	\begin{aligned}
	\varphi_{a}&\to \varphi_{a}+2\pi\\
	\varphi_{b}&\to \varphi_{b}
	\end{aligned}
$$
l'angolo tra $b$ e $z$ torna indietro dopo mezzo giro intorno ad $a$ e resta invariato dopo un giro completo.

![[Pasted image 20260930170729.png]]

allora dopo un giro completo:
$$
	\log\left( \frac{{z-a}}{z-b} \right)\to \log |\frac{{z-a}}{z-b}| + i (\varphi_{a}-\varphi_{b})+i{2}\pi n + i 2\pi
$$
dunque $a$ è un punto di diramazione (di ordine infinito). Girando attorno a $b$ ottengo lo stesso risultato. Non solo, girando in senso antiorario attorno ad $a$ passo al foglio successivo mentre girando intorno a $b$ passo al precedente. (Ha senso se guardo al disegno della spirale).

Dal disegno si verifica facilmente che  $z=0$ o a $z=c$ con $c \in \mathbb{R}$ non sono punti di diramazione.
Cosa succede invece girando intorno a $\infty$?
Ricordando che girare attorno all'infinito equivale a girare in senso orario lungo una circonferenza larga abbastanza da includere tutti i punti che ci interessano possiamo fare il seguente schema:

![[Pasted image 20260930171519.png]]

$$
	\implies \log\left( \frac{{z-a}}{z-b} \right)=\log | \frac{{z-a}}{z-b}|+i 2\pi n +i 2\pi-i 2\pi 
$$
Dunque $z=\infty$ non è un punto di diramazione.

3. Studio lo sviluppo in serie
$$
	\log \frac{{z-a}}{z-b} = \log\left( 1-\frac{a}{z} \right)-\log\left( 1-\frac{b}{z} \right)
$$
ricordando che $\log(1-w)=-\sum^\infty_{n=1} \frac{1}{n} w^n$ per $|w|<1$, visto che $| \frac{a}{z}|$ e $| \frac{b}{z}|<1$ per $z\to \infty$, otteniamo:
$$
	\log \frac{{z-a}}{z-b} = -\sum^\infty_{k=1} \frac{1}{k} \left[ \left( \frac{a}{z} \right)^k-\left( \frac{b}{z} \right)^k \right]
$$
la serie contiene solo potenze negative dunque è una serie di taylor attorno all'infinito, dunque l'infinito è un punto regolare.

- **Oss:** questo sviluppo è la continuazione analitica dello sviluppo di $\log x$ dunque è lo sviluppo sul foglio 0. Lo sviluppo sul foglio $n$-esimo sarà:
$$
		\log \frac{{z-a}}{z-b} = -\sum^\infty_{k=1} \frac{1}{k} \left[ \left( \frac{a}{z} \right)^k-\left( \frac{b}{z} \right)^k \right]+i 2\pi n
$$
si tratta sempre di uno sviluppo di Taylor, dunque è sempre regolare all'$\infty$.

##### Studio dell'analiticità e della polidromia

Una volta studiati i punti di diramazione occupiamoci ora di uno studio di funzione più generico.

Come esempio consideriamo sempre:
$$
	f(z)=\log \frac{{z-a}}{z-b}
$$
Procediamo a step:
1. Per prima cosa verifico se la funzione sia polidroma o monodroma, per farlo vado a cercare i punti di diramazione come appena mostrato.
2. Studio l'analiticità della funzione. Per farlo vado a studiare i singoli fogli.
Per studiare i singoli fogli devo per prima cosa scegliere i tagli. Nel nostro esempio ho 2 possibili opzioni:

 ![[Pasted image 20260930172722.png]]

Nel caso di $\log z$ abbiamo visto che i tagli venivano fissati dall'intervallo di $\theta=arg(z)$.
In questo caso la scelta dei tagli equivale a fissare come variano gli angoli $\varphi_{a} \text{ e } \varphi_{b}$.

Studiamo la scelta $1$, nell'ipotesi in cui $a,b \in \mathbb{R}$.

![[Pasted image 20260930173034.png]]

se scelgo $z\in \mathbb{R}$, con $z>b>a$, $\implies \varphi_{a}-\varphi_{b}=0$ e posso scegliere arbitrariamente $\varphi_{a}=\varphi_{b}=0$.
Dunque (avendo scelto $\varphi_{a,b}=0$):
$$
	\log \frac{{z-a}}{z-b}=\log | \frac{{z-a}}{z-b}|+i 2\pi n
$$
Per andare a studiare cosa succede sul taglio, porto $z$ in prossimità del taglio stesso, passando per un cammino continuo che NON lo attraversi.

![[Pasted image 20260930173329.png]]

Facendo riferimento alla figura, passiamo da sopra. $a<z_{+}<b$. Dopo lo spostamento abbiamo:
$$
	\to \log \frac{{z-a}}{z-b}=\log | \frac{{z-a}}{z-b}|-i\pi+i2\pi n
$$
Se invece passo da sotto il taglio avrò:
$$
		\to \log \frac{{z-a}}{z-b}=\log | \frac{{z-a}}{z-b}|+i\pi+i2\pi n
$$
e come prima ottengo $L_{z}^- -L_{z}^+=2\pi i$.
Per uno studio di questo tipo non mi interessa il tipo di cammino che percorro ma solo come arrivo al taglio (da prima o da dopo) e che non lo attraversi, sotto queste condizioni ottengo sempre lo stesso risultato.
Studiamo ad esempio il caso in cui arrivo da sotto facendo mezzo giro in più:

![[Pasted image 20260930173923.png]]

Ottengo nuovamente:
$$
	\log \frac{{z-a}}{z-b}=\log | \frac{{z-a}}{z-b}|+i\pi+i2\pi n
$$

Occupiamoci dello studio della scelta numero 2 e verifichiamo che sia altrettanto consistente.
Posso nuovamente fissare $\varphi_{a}=\varphi_{b}=0$ quando $a,b,z \in R, \, z>b>a$.
Porto $z$ tra $a$ e $b$ passando da sopra:

![[Pasted image 20261004171556.png]]

Il risultato è:
$$
	f(z)=\log |\frac{z-a}{z-b}|+i\pi+i 2\pi n
$$
Se facessi un mezzo giro in più e ci arrivassi da sotto avrei sempre $\varphi_{a}= 0$ e $\varphi_{b}=\pi$, cioè non ho la discontinuità tra $a$ e $b$ (ricorda il disegno in cui si fa un giro attorno all'infinito).

Studiamo cosa succede sul taglio. Parto da $z$ sopra il taglio, per il quale trovo:
$$
	f_{+}=\log |\frac{z-a}{z-b}|+i 2\pi n
$$
Porto $z$ sotto il taglio senza attraversare alcun taglio.

![[Pasted image 20261004172213.png]]

Il risultato è: 
$$
	f_{-}=\log |\frac{z-a}{z-b}|-i 2\pi n+i 2\pi n
$$
Ho ritrovato nuovamente la differenza di $i 2\pi$ sul taglio. Dunque questa scelta è consistente con la prima.

**Lezione Associata:** [[2.Funzioni polidrome]]