
### Distribuzione Marginale

Immaginiamo adesso di conoscere la probabilità congiunta di un set di variabili aleatorie: $p_{X_{1},X_{2},\dots X_{N}}(x_{1},x_{2},\dots x_{n})$ e di non essere interessati a tutte le variabili ma solo ad alcune di esse.
Possiamo riscrivere $p_{X_{1},X_{2},\dots X_{N-1}}$ indipendentemente dalla probabilità di $p_{X_{N}}$ nel seguente modo:
$$
	p_{N-1}(x_{1},x_{2},\dots x_{N-1}) := \int dx_{n}\, p_{N}(x_{1},x_{2},\dots,x_{N})
$$
La densità di probabilità $p_{N-1}$ così definita viene chiamata densità di probabilità marginale.

### Correlazione e indipendenza di 2 variabili aleatorie

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


**Lezione Associata:** [[4.Distribuzioni di Probabilità continue (di variabili aleatorie)]]