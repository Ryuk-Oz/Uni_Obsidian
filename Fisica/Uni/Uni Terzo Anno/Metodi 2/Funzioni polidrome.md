---
corso: Metodi 2
data: 2026-09-28
tags:
  - lezione
argomenti:
  - Analisi Complessa
lezione-precedente: "[[Mappe conformi e Continuazione Analitica]]"
source:
---


> [!info] Contesto
> Corso: metodi 2
> Argomenti previsti: 

## Riassunto veloce

In questa sezione ci siamo occupati dello studio di funzioni polidrome, in particolare concentrandoci sull'estensione al campo complesso di funzioni "standard" in campo reale che diventano patologiche quando estese al campo complesso. Patologiche in quanto associano punti che vivono in vari piani complessi allo stesso punto. Sono cioè funzioni $\mathbb{C}^n\to \mathbb{C}$.
Per affrontare questo problema abbiamo utilizzato 2 approcci. Il primo consiste nel restringere il dominio della funzione ad un solo piano. Questo approccio presenta però alcune problematiche, in particolare incontriamo sempre una semiretta (taglio) lungo la quale la funzione in questione è discontinua. I punti di inizio e fine del taglio si chiamano punti di diramazione.
Per risolvere questo problema abbiamo adottato un secondo approccio, quello di considerare tutte le copie di $\mathbb{C}^n$, andando a incollare i vari piani/fogli tra di loro in concomitanza dei tagli. Così facendo siamo andati a costruire delle superfici proprie della funzione, le superfici Riemanniane, sulle quali funzioni precedentemente polidrome diventano monodrome e analitiche ovunque (tranne che nei punti di diramazione e in eventuali singolarità di altro tipo).
Questo studio è stato portato avanti studiando alcuni esempi interessanti come $\sqrt{ z }$ e $\log z$.
Infine ci siamo occupati anche dello studio di funzione di funzioni di questo tipo.

## Appunti

Iniziamo adesso lo studio di un grande gruppo di funzioni "patologiche", le funzioni polidrome.

#### Funzione radice quadrata

Partiamo dallo studio di un esempio semplice:
$$
	w=f(z)=z^2 \quad \Rightarrow \quad z=\pm\sqrt{ w }
$$
Come discusso nella lezione precedente, questa funzione manda una copia di $\mathbb{C}_{z}\to\mathbb{C}_{w}^2$ e mi da problemi ad invertire.

![[Pasted image 20260928231002.png]]

posso riscrivere la mappa $f(z)=z^2$ nel seguente modo:
$$
	f: \mathbb{C}\to \Pi=\Omega\cap \Omega'
$$
dove $\Omega$ e $\Omega'$ sono due copie distinte del piano complesso, che chiamiamo fogli.

 Un'idea per potere definire un'inversa è quella di scegliere di invertire soltanto su uno dei due fogli, che chiamo *foglio fondamentale*, gli altri sono detti fogli successivi. Scegliamo in questo caso $\Omega$.
 Andiamo dunque a definire $\Omega$:
 $$
	\begin{aligned}
	\Omega&=\{ w\in\mathbb{C}: 0\leq arg(w) <2\pi \} \quad \text{scelta (1)} \\
	\Omega&=\{ w\in\mathbb{C}: -\pi\leq arg(w) <\pi \} \quad \text{scelta (2)} 
	\end{aligned}
 $$
 Concentriamoci momentaneamente sulla scelta $(1)$.
 A $0\leq arg(w)<2\pi$ corrisponde $0\leq arg(z)<\pi$, cioè solo i valori di $z$ con parte immaginaria positiva ($\mathrm{Im}(z)>0$).
 Consideriamo ad esempio $w=4$ e $w=-4$:
 $$
	\begin{aligned}
	w&=4\to|4|,arg=0 \to z=2 \\
	w&=-4\to |4|,arg=\pi \to z=2i
	\end{aligned}
 $$
 calcolandolo esplicitamente:
 $$
	\sqrt{ -4 }=(4e^{i\pi})^{1/2}=2e^{i\pi/2}=2i
 $$
 non posso andare a scegliere $-4=4e^{-i\pi}$ perchè $-\pi$ esce fuori da $\Omega$, cioè fissato $\Omega$ ho reso univoca la scelta della fase di $w$, risolvendo il problema di partenza.
 Facendo la scelta $(2)$ otterrei $-\frac{\pi}{2}\leq arg(z)\leq \frac{\pi}{2}$ e questa volta seleziono $\mathrm{Re}(z)>0$.
 In maniera analoga, posso andare a fare qualunque scelta di intervallo per il mio foglio principale.
 Tuttavia questo approccio non è il migliore e presenta alcune problematiche.
 
 Studiando il caso $(1)$ troviamo una discontinuità sul semiasse reale da cui parto a contare l'angolo, cioè $\sqrt{ w }$ non è analitica ovunque.
 $$
	\begin{aligned}
	\lim_{ \varepsilon \to 0 } \sqrt{ w^+ }&=\lim_{ \varepsilon \to 0 } \sqrt{ \rho e^{i\varepsilon} }=\sqrt{ \rho } \\
	\lim_{ \varepsilon \to 0 } \sqrt{ w^- }&=\lim_{ \varepsilon \to 0 } \sqrt{ \rho e^{i(2\pi-\varepsilon)} }=-\sqrt{\rho }  
	\end{aligned}
 $$
 ![[Pasted image 20260929000055.png]]

Facendo la scelta $(2)$, la discontinuità si sposta sul semiasse reale negativo ma non scompare. Cambiando la scelta di $\Omega$ posso spostare la discontinuità dove voglio, ma non posso mai eliminarla. Lo stesso problema di ha ovviamente per $\Omega'$.
La linea di discontinuità prende  il nome di **taglio** e i punti da cui partono questi tagli si chiamano **punti di diramazione**.

Cerchiamo una soluzione a questo problema. Proviamo a definire l'inversa andando ad utilizzare più fogli. Quello che otterremo è una funzione continua in cui il valore sul taglio di un foglio arrivando "dal basso" è uguale al valore sul secondo foglio arrivando "dall'alto", questo ci permette di "incollare" i fogli e andare a definire una funzione il cui dominio passa da un foglio all'altro in corrispondenza dei punti di diramazione. In questa sezione ci occuperemo di formalizzare più efficacemnete questa idea andando a studiare le funzioni cosìdette **polidrome**, come renderle monodrome e come studiarle dopo averle rese tali.

La seguente immagine da una buona idea di quello che andiamo a operare sul dominio.
![[Pasted image 20260929000847.png]]
"Formalizziamo" quanto discusso andando a vedere un ulteriore esempio, quello della funzione logaritmo in campo complesso.

#### Funzione logaritmo

consideriamo la funzione logaritmo: 
$$
	w=f(z)=\log z; \quad z=|z|e^{i\theta}
$$
l'idea da cui partiamo per lo studio del logaritmo complesso è quella di studiarlo come continuazione analitica del logaritmo reale $\log x$ con $x \in \mathbb{R}$.

Sappiamo che la funzione esponenziale complessa $z=e^w$ è una mappa $\mathbb{C}_{z}\to\mathbb{C}_{w}^\infty$, dunque $\log z$ definito come l'inverso della funzione esponenziale è mal definito.

##### 1) Provo a limitare il dominio

Come per la radice proviamo a definire l'inversa limitando l'intervallo di $\theta$ ammessi:
$$
	\theta\in I_{2\pi}: -\pi<\theta\leq \pi
$$
e otteniamo la funzione
$$
	w=\log z=\log(|z|e^{i\theta})=\log |z| + i\theta
$$
che è una possibile continuazione analitica di $\log x$ perchè le due funzioni coincidono in $\mathbb{R}^+$ (che contiene infiniti punti di accumulazione) per $\theta=0$.
Il dominio di $w$ è una striscia di ampiezza $2\pi$.

![[Pasted image 20260930145524.png]]

Esattamente come succedeva per la radice, $\log z=\log |z|+i\theta$ ha un taglio.
Con questo intervallo di $\theta$ la funzione è definita su $\mathbb{C}-\{ \mathbb{R}_{-} \}=D_{1}$; su $\mathbb{R_{-}}$ ho un taglio.

![[Pasted image 20260930145823.png|583]]

Andiamo a verificarlo:
$$
	\begin{aligned}
	L_{+}&=\lim_{ \varepsilon \to 0 }(\log(\rho e^{i(\pi-\varepsilon)}))=\log \rho + i\pi \\ 
	L_{-}&=\lim_{ \varepsilon \to 0 } (\log(\rho e^{i(-\pi+\varepsilon)}))=\log \rho-i\pi \\
	L_{+}-L_{-}&=2\pi i
	\end{aligned}
$$
Il taglio resta presente qualunque sia la scelta di $I_{2\pi}$, dunque andando a definire l'inversa così, ho sempre una regione (il taglio) in cui la funzione logaritmo non è analitica.

Andando ad esempio a scegliere $-\frac{\pi}{2}<\theta\leq \frac{3\pi}{2}$ ho:

![[Pasted image 20260930150410.png]]

$$
	\begin{aligned}
	L_{R}&=\lim_{ \varepsilon \to 0 } (\log(\rho e^{i(-\pi/2+\varepsilon)}))=\log \rho-\frac{i\pi}{2}\\
	L_{{L}}&=\lim_{ \varepsilon \to 0 } (\log \rho e^{i(3\pi/2-\varepsilon)})=\log \rho + i\frac{3}{2}\pi\\
	L_{L}-L_{R}&=2\pi i 
	\end{aligned}
$$
La funzione è definita su $\mathbb{C}-\{ I^{-} \}=D_{2}$
la differenza tra i 2 valori che assume la funzione prima e dopo il taglio resta uguale.

Si nota subito che le due scelte non sono completamente sovrapponibili.

![[Pasted image 20260930151123.png]]

Sappiamo dai teoremi studiati in precedenza che in $D_{C}$ le due funzioni devono coincidere, verifichiamolo:
$$
	\begin{aligned}
	\log(i) &=^1 \log(1e^{i\pi/2}) = \frac{i\pi}{2} \\
	&=^2 \log(1e^{i\pi/2})=\frac{i\pi}{2}
	\end{aligned}
$$
Se invece scelgo $z_{0} \in D_{NC}$, le due funzioni saranno diverse:
$$ \begin{aligned}
z_{0}=-\frac{1}{\sqrt{ 2 }}-\frac{i}{\sqrt{ 2 }} &=^1 1e^{-i 3/2 \pi} \to \log z_{0} = -i \frac{3}{2}\pi \\
&=^2 1e^{i 5/4 \pi}\to \log z_{0}=i \frac{5}{4}\pi 
\end{aligned}
$$
- **Oss:** la scelta $2\pi<\theta\leq{4}\pi$ non è una buona scelta per definire il logaritmo complesso perchè non coincide con $\log x$ da nessuna parte, quindi non mi restituisce una continuazione analitica del logaritmo reale.

Come fatto anche per la radice quadrata, cambiamo approccio per provare a risolvere questi problemi.

##### 2) Considero tutte le $\infty$ copie di $\mathbb{C}_{z}$

In maniera molto poco formale considero $-\infty<\theta<\infty$.
Più formalmente mappo $\theta \to \theta+2\pi n$ e vado a definire vari "piani/fogli". Ad esempio:
$$
	\begin{aligned}
	\text{Foglio zero:} &\quad 0\leq \theta_{0}<2\pi\\
	\text{Foglio n-esimo:} &\quad\theta_{0}\leq \theta_{n}<\theta_{0}+2\pi n
	\end{aligned}
$$
In questo caso il dominio diventa $\Pi = \cup_{i}\mathbb{C}_{i}$, superficie di Riemann del logaritmo.
$$
	\log z|_{n} = L_{n}(z)= \log \rho + i\theta+i 2\pi n; \quad n\in \mathbb{Z}
$$
Ogni foglio avrà il proprio taglio su $\mathbb{R}^{+}$.
Infatti, per un qualunque $n$ fissato abbiamo:
$$
	\begin{aligned}
	L_{n}^+&=\log \rho + i{2}\pi n \\
	L_{n}^-&=\log \rho + i_{2}\pi +i{2}\pi n \\
	\implies L_{n}^- - L_{n}^+ &= 2\pi i
	\end{aligned}
$$
dal calcolo esplicito notiamo che $L_{n}^-=L_{n+1}^+$. Dunque se costruisco $\Pi$ come una superficie il cui lembo inferiore del foglio $n$-esimo si incolla al lembo superiore del foglio $n+1$-esimo ottengo una funzione continua. Questa superficie prende il nome di **Superficie di Riemann** (del logaritmo).

![[Pasted image 20260930163714.png|405]]

Pertanto la funzione $\log z$ definita sulla superficie di Riemann:
$$
	f:\Pi\to \mathbb{C}
$$
non è più una funzione polidroma ma diventa una funzione **globalmente analitica**.

- **NOTA BENE:** potremmo andare a definire $\phi(z)\equiv\log z$ come:
$$
	\phi(z)=\int^z_{1} \frac{1}{z'} \, dz'
$$
e otterremo lo stesso risultato. Infatti, andando ad integrare lungo una curva $\gamma_{n}$ che gira $n$ volte attorno all'origine , il valore di $\phi(z)$ finisce varia col numero di giri che compiamo, aumentando di $i 2\pi n$ ad ogni giro.

- **Oss:** ogni funzione polidroma necessita di una superficie di Riemann costruita ad-hoc per essere resa globalmente analitica.

#### Studio dei punti di diramazione

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

#### Studio di funzioni polidrome

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

## Domande per revisione
- [ ] 

## Collegamenti
- Lezione precedente: [[Mappe conformi e Continuazione Analitica]]
- Concetti collegati: [[]]