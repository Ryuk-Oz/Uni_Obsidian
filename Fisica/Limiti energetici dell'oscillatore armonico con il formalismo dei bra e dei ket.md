
**Utili per la comprensione:** [[Insiemi completi di osservabili compatibili]], [[Commutatori e relazioni di indeterminazione]]

Ririsolviamo l'oscillatore armonico usando l'algebra lineare.

Il problema è definito dalla sua Hamiltoniana:
$$
	H= \frac{p^2}{2m} +\frac{1}{2} m \omega^2 x^2
$$
Adesso $x$, $p$ e $H$ sono operatori e $[x,p]=i\hbar$.
Devo costruire un ICOC, qual è l'osservabile piuù furba per costruire il nostro ICOC?
A noi interessa lo studio di stati stazionari in una dimensione, sappiamo che ogni stato stazionario è completamente definito dalla sua energia. Ha dunque scegliere come ICOC il solo operatore Hamiltoniano: $\{ H \}$.

Riscrivo l'equazione agli autovalori:
$$
	H \ket{n} =E_{n} \ket{n} 
$$
con $\langle n|m \rangle=\delta_{nm}$ e $\sum_{n} \ket{n}\bra{n}=\mathbb{1}$.

E ho tutto il necessario a risolvere il sistema.
Osservazioni preliminari:
- $E_{n}>0$ $\forall n$:
$$
	\begin{aligned}
	E_{n}&=\bra{n} H \ket{n} = \frac{1}{2m} \bra{n} p^2 \ket{n} + \frac{1}{2}m\omega^2 \bra{n} x^2 \ket{n} \\
	&=\frac{1}{2m}[(\Delta_{n}p)^2+\bra{n} p\ket{n} ^2]+\frac{1}{2} m\omega^2 [(\Delta_{n}x)^2+\bra{n} x\ket{n} ^2]\geq \frac{1}{2m}(\Delta_{n}p)^2+ \frac{1}{2 }m\omega^2 (\Delta_{n}x)^2>0
	\end{aligned}
  $$
  L'ultima disuguaglianza è data dal principio di indeterminazione
  
Qual è il valore minimo di energia compatibile? Continuando la catena di disuguaglianze otteniamo:
$$
	E_{n}\geq \frac{1}{2m} (\Delta_{n}p)^2+\frac{1}{2} m\omega^2 \frac{\hbar^2}{4(\Delta_{n}p)^2}
$$
Sia $(\Delta_{n}p)^2\equiv z$ e cerco il minimo di:
$$
	\frac{z}{2m}+\frac{\hbar^2m\omega^2}{8} \frac{1}{z} \implies \frac{1}{2m}-\frac{\hbar^2m\omega^2}{8} \frac{1}{z^2}=0
$$
Troviamo:
$$
	z= \frac{1}{2} m\hbar \omega = (\Delta_{n}p)^2
$$
Pertanto:
$$
	(E_{n})_{min}=\frac{1}{2m} \frac{1}{2} m\omega \hbar + \frac{\hbar^2m\omega^2}{8} \frac{2}{m\omega \hbar} = \hbar \frac{\omega}{2}
$$

Possiamo trovare lo stesso risultato partendo dal commutatore (infatti il commutatore è quello che mi da il principio di indeterminazione).
$$
	\begin{aligned}
	E_{n}&=\bra{n} H \ket{n} = \frac{1}{2m} \bra{n} p^2 \ket{n} + \frac{1}{2}m\omega^2 \bra{n} x^2 \ket{n} \\
	&= \frac{1}{2m} \sum_{k} [ \bra{n}p\ket{k} \bra{k} p\ket{n} +m^2\omega^2 \bra{n} x\ket{k} \bra{k} x\ket{n}  ]\\
	&= \frac{1}{2m} \sum_{k} \left[ |\bra{n} p\ket{k} |^2+m^2 \omega^2 |\bra{n} x\ket{k} |^2 \right] \overset{?}{=}0\iff \bra{n} p\ket{k} =\bra{n} x\ket{k} =0\; \forall \ket{k} 
	\end{aligned}
$$
Ora sfrutto il commutatore:
$$
	[x,p]=i\hbar \implies i\hbar=\bra{n} xp-px \ket{n} =\sum_{k} [\bra{n} x\ket{k} \bra{k} x\ket{n}-\bra{n} p \ket{k} \bra{k} x \ket{n} ] \neq 0 
$$
Dunque $E_{n}$ è necessariamente diverso (maggiore) di $0$.

- Gli autovalori $E_{n}$ sono spaziati di $\hbar \omega$.
  Per dimostrarlo usiamo i commutatori:
$$
	\begin{cases}
	[x,H]= i\hbar \frac{p}{m} \\
	[p,H]= -i\hbar m\omega^2x 
	\end{cases}
$$
  Guardiamo come sono fatti gli elementi di matrice dei commutatori:  
$$
	\begin{aligned}
	\bra{k} [x,H] \ket{l} &=\frac{i\hbar}{m} \bra{k} p\ket{l}\\
	&=\bra{k} xH-Hx \ket{l}=(E_{l}-E_{k})\bra{k} x \ket{l}  
	\end{aligned}
  $$
  Idem per l'altro:
$$
	\begin{aligned}
	\bra{k} [p,H]\ket{l} &=  -i\hbar m\omega^2 \bra{k} x \ket{l}\\
	&= \bra{k} pH-Hp \ket{l} = (E_{l}-E_{k}) \bra{k} p \ket{l}  
	\end{aligned}
$$
  Mettendo insieme otteniamo un sistema lineare:
$$
	\begin{cases}
	(E_{l}-E_{k})\bra{k} x \ket{l} -\frac{i\hbar}{m} \bra{k} p \ket{l} =0 \\
	i\hbar m\omega^2 \bra{k} x \ket{l} +(E_{l}-E_{k}) \bra{k} p \ket{l} =0 \\
	\end{cases}
$$
  Entrambe sono uguali a 0 e ho due possibilità, la prima è che $\bra{k}p\ket{l}=\bra{k}x\ket{l}=0$.
  L'altra è che il determinante del sistema sia $0$:
$$
	(E_{l}-E_{k})^2-\hbar^2 \omega^2 =0 \implies E_{l}-E_{k}= \pm \hbar \omega
  $$
  La soluzione evidente è una serie di autostati che differiscono tra loro di $\hbar \omega$.
  Questi sono tutti gli stati? Potrebbe esistere uno stato $\ket{n_{0}}$ t.c. $E_{n_{0}}-E_{l} \neq \hbar \omega\; \forall l$?
  Non esiste perchè violerebbe il principio di indeterminazione:
$$
	i\hbar = \bra{n_{0}} [x,p]\ket{n_{0}}= \sum_{k} [\bra{n_{0}} x \ket{k} \bra{k} p\ket{n_{0}}-\bra{n_{0}} p\ket{k} \bra{k} x \ket{n_{0}}   ]=0  
  $$
**Lezione associata:** [[7. Oscillatore armonico quantistico (con la teoria degli operatori)]]
