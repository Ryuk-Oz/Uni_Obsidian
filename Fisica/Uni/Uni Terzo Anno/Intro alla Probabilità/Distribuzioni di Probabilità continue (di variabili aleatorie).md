---
corso: Probabilità
data: 2026-10-04
tags:
  - lezione
argomenti:
  - Probabilità
  - Distribuzioni di Probabilità
lezione-precedente: "[[Processi di ramificazione]]"
source:
---


> [!info] Contesto
> Corso: undefined
> Argomenti previsti: 

## Riassunto veloce



## Appunti

Spostiamo momentaneamente il nostro studio dalla probabilità di processi discreti a processi continui, come quelli su cui siamo abituati a lavorare in analisi dati. Concentriamoci in particolare su alcuni esempi di base per poi affrontare alcuni teoremi importanti.

#### Cambi di variabili aleatorie

Iniziamo illustrando un semplice risultato che ritorna in continuazione, affrontiamo il problema dei cambi di variabile che siamo abituati ad usare in analisi, applicato a distribuzioni di probabilità

Consideriamo $X$, variabile aleatoria. Sia $p_{X}(x)$ la densità di probabilità associata a questa variabile. (Dunque $p_{X}(x)dx=P[x\leq X\leq x+dx]$).
Sia $y=f(x)$ una qualunque funzione invertibile. Qual è la densità di probabilità $p_{Y}(y)$?

![[Pasted image 20261007152600.png|532]]

Anche cambiando variabile la probabilità finale deve restare invariata, dunque:
$$
	P[x\leq X\leq x+dx]=P[y\leq Y\leq y+dy] \implies p_{X}(x)dx=p_{Y}(y)dy
$$
a questo punto sfruttiamo i teoremi dell'analisi classica:
$$p_{Y}(y)=p_{X}(x) | \frac{dx}{dy}| =p_{X}(x) \frac{1}{|f'(x)|}$$
In più dimensioni facciamo uso del determinante del Jacobiano, come sempre.

Facciamo subito un esempio pratico. Partiamo dalla Gaussiana: $p_{X}(x)=\frac{1}{\sqrt{ 2\pi }}e^{ -x^2/2 }$.
Consideriamo $y=x^2=f(x) \implies f'(x)=2x=2 \sqrt{ y }$ e applichiamo quanto appena detto.
$$
	p_{Y}(y)=\frac{1}{\sqrt{ 2\pi }}e^{ -y/2 } \frac{1}{2\sqrt{ y }}=\frac{1}{2\sqrt{ 2\pi y }}e^{ -y/2 }
$$
e abbiamo ottenuto la distribuzione $\chi^2$ con $k=1$.

![[Pasted image 20261007153305.png]]

#### Distribuzione Marginale

Immaginiamo adesso di conoscere la probabilità congiunta di un set di variabili aleatorie: $p_{X_{1},X_{2},\dots X_{N}}(x_{1},x_{2},\dots x_{n})$ e di non essere interessati a tutte le variabili ma solo ad alcune di esse.
Possiamo riscrivere $p_{X_{1},X_{2},\dots X_{N-1}}$ indipendentemente dalla probabilità di $p_{X_{N}}$ nel seguente modo:
$$
	p_{N-1}(x_{1},x_{2},\dots x_{N-1}) := \int dx_{n}\, p_{N}(x_{1},x_{2},\dots,x_{N})
$$
La densità di probabilità $p_{N-1}$ così definita viene chiamata densità di probabilità marginale.

#### Correlazione e indipendenza di 2 variabili aleatorie

Come ultimo tassello prima della discussione dei teoremi fondamentali, introduciamo i concetti di correlazione e indipendenza tra variabili aleatorie.
Consideriamo 2 eventi $X,Y$ con associata una densità di probabilità $p_{X}(x)$ e $p_{Y}(y)$.

Si dice che $X$ e $Y$ sono **indipendenti** $\iff p_{X,Y}(x,y)=p_{X}(x)p_{Y}(y)$.
Una formulazione alternativa che fa uso della marginale è la seguente:
$$
	p(x,y)=\left[ \int dx\,p(x,y) \right]\left[ \int dy\,p(x,y) \right]
$$
che è esattamente la stessa cosa.

Si dice invece che $X$ e $Y$ sono **scorrelate** $\iff E[XY]=E(X)E(Y)$.

**Achtung!** Le 2 cose non sono tra di loro equivalenti; l'indipendenza implica sempre scorrelazione ma non vale il viceversa.

#### Probabilità condizionata in distribuzioni continue: Il paradosso di Borel-Kolmogorov

Occupiamoci ora dello studio della probabilità condizionata nel caso continuo. Nel caso continuo la probabilità di un evento $X$ crolla a 0 e ha misura nulla rispetto allo spazio degli eventi, questo causa dei problemi, che adesso analizzeremo in un caso semplice.
Consideriamo una sfera di raggio $R$ e studiamo la probabilità di trovarci in un punto preciso su di un cerchio massimo, sapendo di trovarci già su un cerchio massimo. Quello che troviamo è che cambiando il cerchio massimo considerato cambia anche la probabilità condizionata che stiamo cercando di calcolare. Inutile dire che questo è un bel problema.
Studiamo un modello bidimensionale semplificato per capire quale sia l'origine del problema.
Considero la semicirconferenza di raggio unitario in figura.

![[Pasted image 20261008085649.png|548]]

Ipotizziamo una distribuzione di probabilità uniforme all'interno della circonferenza:
$$
	p_{X,Y}(x,y)=\frac{2}{\pi}; \quad \int_{S}dxdy\,p_{X,Y}(x,y)=1
$$
Qual è la probabilità di trovarsi sulla metà superiore del raggio?
Intuitivamente, poichè la distribuzione è uniforme, ci verrebbe da pensare:
$$
	P\left( Y\geq \frac{1}{2}|X=0 \right)=\frac{1}{2}
$$
Ma il raggio ha misura nulla rispetto al semicerchio quindi questa probabilità è più complessa da calcolare di quanto sembri.
$$
	\begin{aligned}
	P\left( Y\geq \frac{1}{2}|X=0 \right)&=\int^1_{\frac{1}{2}} p(y|x=0)\,dy \overset{P. cond.}{=} \frac{2}{\pi}\int^1_{\frac{1}{2}} \frac{p_{XY}(x=0,y)}{p_{X}(x=0)}\, dy \\
	\text{calcolo la densità di} &\text{ probabilità marginale } p_{X}(x=0) : \\
	p_{x}(x=0)&=\int_{0}^1 p_{XY}(x=0,y)\,dy=\frac{2}{\pi}\int^1_{0}dy=\frac{2}{\pi}\\
	\implies P\left( Y\geq \frac{1}{2}|X=0 \right)&=\int^1_{\frac{1}{2}} \frac{2/\pi}{2/\pi}\,dy = \frac{1}{2}
	\end{aligned}
$$
E abbiamo ottenuto il risultato che ci aspettavamo.
Proviamo ora a rifare il calcolo in coordinate polari. Sappiamo che $\det J(r,\theta)=r$, per cui:
$$
	p_{r,\theta}(r.\theta)=\frac{2}{\pi}r
$$
La probabilità di trovarci sulla metà superiore del raggio diventa adesso:
$$
	\begin{aligned}
	P\left( r\geq \frac{1}{2}|\theta=\frac{\pi}{2} \right)&=\int^1_{\frac{1}{2}} p_{r\theta}\left(r,\theta=\frac{\pi}{2}\right) \, dr = \int^1_{\frac{1}{2}} \frac{p_{r\theta}(r=0,\theta)}{p_{r}(r=0)}\,dr\\
	p_{r}(r=0)&=\int^1_{0} p_{r\theta}\left( r,\theta=\frac{\pi}{2} \right)\,dr=\int_{0}^1 \frac{2}{\pi}r\,dr=\frac{1}{\pi}\\
	\implies P\left( r\geq \frac{1}{2}|\theta=\frac{\pi}{2} \right)&=\int^1_{\frac{1}{2}} \frac{2\pi/r}{1/\pi}\,dr = \int^1_{\frac{1}{2}} 2r \, dr = r^2|^1_{\frac{1}{2}}=\frac{3}{4}
	\end{aligned}
$$
Abbiamo ottenuto due probabilità diverse. Questo risultato è ovviamente paradossale. Proviamo ad investigarne la causa. Il problema è situato proprio nella misura nulla del raggio. Se consideriamo un intervallo attorno al raggio e lo mandiamo a 0, ci osserviamo che nelle 2 rappresentazioni diverse, gli intervalli che consideriamo sono profondamente diversi e dunque è diversa la probabilità.

![[Pasted image 20261008092344.png]]

Il modo di trattare questo paradosso è molto complesso e difficilmente in scenari reali ci capiterà di incontrare questi problemi. (Per curiosità vedere le $\sigma$-algebre).


## Domande per revisione
- [ ] 

## Collegamenti
- Lezione precedente: [[Processi di ramificazione]]
- Concetti collegati: [[Introduzione e concetti base di teoria della probabilità]], [[Probabilità condizionata]]

