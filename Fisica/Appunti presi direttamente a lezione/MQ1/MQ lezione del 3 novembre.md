
Ricorda: $$
	\frac{d}{dt} \langle Q \rangle _{\alpha} = \langle  \frac{ \partial Q }{ \partial t }  \rangle _{\alpha} +\frac{i}{\hbar} \langle [H,Q] \rangle _{\alpha}
 $$

Riprendiamo la corrispondenza tra parentesi di poisson e commutatore:
$$
	\begin{cases}
	\{ x_{i},  p_{j}  \}=\delta_{ij} \\
	[\hat{x}_{i}, \hat{p}_{j}]=i\hbar \delta_{ij}
	\end{cases}
$$
### Principio di indeterminazione per l'energia e il tempo

$$
	\Delta_{\alpha}E \cdot \Delta_{\alpha}t \geq \frac{\hbar}{2}$$
$\forall Q$ t.c $\frac{ \partial Q }{ \partial t }=0$ posso scrivere:
$$
	\Delta_{\alpha}E \cdot \Delta_{\alpha}Q \geq \frac{1}{2} |\langle -i[H,Q] \rangle _{\alpha}|=\frac{\hbar}{2} \left| \frac{d}{dt }\langle Q \rangle _{\alpha}\right|
$$
Dunque:
$$
	\Delta_{\alpha}E \cdot \frac{\Delta_{\alpha}Q}{|d\langle Q \rangle _{\alpha} / dt|}\geq \frac{\hbar}{2}
$$
Posso definire:
$$
	\Delta_{\alpha}^Q t\equiv \frac{\Delta_{\alpha}Q}{|d\langle Q \rangle _{\alpha} / dt|}
$$
che è il tempo impiegato da $\langle Q \rangle_{\alpha}$ per cambiare di una $\sigma$ ($\Delta_{\alpha}Q$), nello stato $\alpha$.
E la formulazione CORRETTA diventa:
$$
	\Delta_{\alpha}E \cdot \Delta_{\alpha}^Q t \geq \frac{\hbar}{2}
$$
Questa cosa non si può definire per stati stazionari, in quando $\langle Q \rangle_{\alpha}$ è costante.


### Ri-risolvere l'oscillatore armonico col formalismo dei braket

Ririsolviamo l'oscillatore armonico usando l'algebra lineare.

Il problema è definito dalla sua Hamiltoniana:
$$
	H= \frac{p^2}{2m} +\frac{1}{2} m \omega^2 x^2
$$
Adesso $x$, $p$ e $H$ sono operatori e $[x,p]=i\hbar$.
Devo costruire un ICOC, qual è l'osservabile piuù furba per costruire il nostro ICOC?
A noi interessa lo studio di stati stazionari $\implies$ ICOC: $\{ H \}$
RIVEDI QUESTA AFFERMAZIONE

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
	E_{n}&=\bra{n} H \ket{n} = \frac{1}{2m} \bra{n} p^2 \ket{n} + \frac{1}{2}m\omega^2 \bra{n} x \ket{n} \\
	&=\frac{1}{2m}[(\Delta_{n}p)^2+\bra{n} p\ket{n} ^2]+\frac{1}{2} m\omega^2 [(\Delta_{n}x)^2+\bra{n} x\ket{n} ^2]\geq \frac{1}{2m}(\Delta_{n}p)^2+ \frac{1}{2 }m\omega^2 (\Delta_{n}x)^2>0
	\end{aligned}
  $$
  L'ultima disuguaglianza è data dal principio di indeterminazione
  
Qual è il valore minimo di energia compatibile? Continuo la catena di disuguaglianze:
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
	E_{n}&=\bra{n} H \ket{n} = \frac{1}{2m} \bra{n} p^2 \ket{n} + \frac{1}{2}m\omega^2 \bra{n} x \ket{n} \\
	&= \frac{1}{2m} \sum_{k} [ \bra{n}p\ket{k} \bra{k} p\ket{n} +m^2\omega^2 \bra{n} x\ket{k} \bra{k} x\ket{n}  ]\\
	&= \frac{1}{2m} \sum_{k} \left[ |\bra{n} p\ket{k} |^2+m^2 \omega^2 |\bra{n} x\ket{k} |^2 \right] \overset{?}{=}0\iff \bra{n} p\ket{n} =\bra{n} x\ket{p} =0\; \forall \ket{k} 
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
	[p,H]= -i\hbar m\omega^2x \quad \text{DIMOSTRA}
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
### Soluzione

Per comodità definisco una nuova Hamiltoniana adimensionale:
$$
	\mathcal{H}= \frac{H}{\hbar \omega}=\frac{1}{2m\omega \hbar}(p^2+m^2\omega^2x^2)
$$
Con autovalori:
$$
	\varepsilon_{n}= \frac{E_{n}}{\hbar \omega} \implies \mathcal{H}\ket{n} =\varepsilon_{n}\ket{n} 
$$
Cerco di fattorizzare l'Hamiltoniana. Definisco un nuovo operatore:
$$
\begin{cases}
	a= \frac{1}{\sqrt{ 2m\hbar \omega }}(p-im\omega x)\\
	a^{\dagger}= \frac{1}{\sqrt{ 2m\hbar \omega }}(p+im\omega x)
\end{cases}
$$
$$
	a^{\dagger}a = \frac{1}{2m\hbar \omega} (p^2+m^2\omega^2x^2+im\omega[x,p])=\mathcal{H}-\frac{1}{2}
$$
Osservazione:
$$
	[a,a^{\dagger}] = \frac{1}{2m\hbar \omega}(-im\omega [x,p]+imw[p,x])=1
$$
$$
	[\mathcal{H},a]=[a^{\dagger}a,a]=a^{\dagger}\cancel{[a,a]}+a[a^{\dagger},a]=-a
$$
$$
	[\mathcal{H},a^{\dagger}]= a^{\dagger}
$$
Queste tre relazioni definiscono l'algebra di Heisenberg:
$$
	\begin{cases}
	[a,a^{\dagger}]=1 \\
	[\mathcal{H},a]=-a \\
	[\mathcal{H},a^{\dagger}]=a^{\dagger}
	\end{cases}
$$
Preso un qualunque stato $\ket{l}$ posso considerare un nuovo stato $a^{\dagger}\ket{l}$. Cosa so sull'energia di questo nuovo stato? Per studiarlo ci faccio agire sopre l'Hamiltoniana:
$$
	\begin{aligned}
	\mathcal{H}[a^{\dagger}\ket{l} ]&= [a^{\dagger}\mathcal{H}+a^{\dagger}]\ket{l} =(\varepsilon_{l}+1)(a^{\dagger}\ket{l} )\\
	\mathcal{H}[a \ket{l} ]&= [a\mathcal{H}-a]\ket{l} = (\varepsilon_{l}-1)(a\ket{l} )
	\end{aligned}
$$
$a^{\dagger}$ e $a$ sono detti operatori gradino / operatodi di creazione e distruzione.
Gli stati $a^{\dagger}\ket{l}$ e $a\ket{l}$ sono autostati di $\mathcal{H}$ con autovalore successivo e precedente rispetto a all'autostato $\ket{l}$.
Ma non posso scendere all'infinito perchè ho dimostrato che l'energia ha un minimo, maggiore di $0$ (cioè $\varepsilon_{n}>0 \; \forall n$). Dunque la sequenza deve terminare.
Dunque deve esistere uno stato $\ket{0}$ t.c $a\ket{0}={0}$, altrimenti $E$ non è limitata inferiormente.
Qual è l'energia di $\ket{0}$?
$$
	\mathcal{H}\ket{0} =\left( a^{\dagger}a+\frac{1}{2} \right)\ket{0}=\frac{1}{2} \ket{0}  
$$
Dunque $\varepsilon_{0}=\frac{1}{2}$, cioè $E_{0}=\frac{1}{2}\hbar \omega$.
$$
	\varepsilon_{n}=\left( n+\frac{1}{2} \right) \implies E_{n}\left( n+\frac{1}{2} \right)\hbar \omega
$$


**Studio di $a$ e $a^{\dagger}$**

$$
	\begin{aligned}
	\bra{k} \mathcal{H}a^{\dagger}\ket{l}& =\varepsilon_{k} \bra{k} a^{\dagger}\ket{l}\\
	  &=\bra{k} \mathcal{H}a^{\dagger}+a^{\dagger}\ket{l} =(\varepsilon_{l}+1) \bra{k} a^{\dagger}\ket{l} 
	\end{aligned}
$$
Dunque:
$$
	(\varepsilon_{k}-(\varepsilon_{l}+1))=\bra{k} a^{\dagger}\ket{l} =0
$$
Dunque $\bra{k}a^{\dagger}\ket{l}=0$ tranne se $\varepsilon_{k}=\varepsilon_{l+1}\implies k=l+1$.
Trovo un analogo per $a$ (completa a casa).
$\bra{k}a\ket{l}=0$ a meno che $k=l-1$.
E vale:
$$
	\bra{l+1} a^{\dagger} \ket{l} ^* = \bra{l} a \ket{l+1} 
$$
Posso riscrivere queste cose come:
$$
	\bra{k} a \ket{l}  = \lambda_{l} \delta_{k,l-1}
$$
e:
$$
	\bra{k} a \ket{l} ^* = \bra{l} a^{\dagger} \ket{k} = \lambda_{l}^* \delta_{k,l-1}
$$
Applichiamo questo a quanto discusso fin'ora:
$$
	\varepsilon_{n}=\left( n+\frac{1}{2} \right)= \bra{n} \mathcal{H} \ket{n}  = \bra{n} a^{\dagger}a \ket{n} +\frac{1}{2}
$$
E:
$$
	\bra{n} a^{\dagger}a \ket{n} = n = \sum_{k} \bra{n} a^{\dagger} \ket{k}  \bra{k} a \ket{n} = \bra{n} a^{\dagger} \ket{n-1} \bra{n-1} a \ket{n}  = |\lambda_{n}|^2 \implies \lambda_{n} = \sqrt{ n }
$$
Adesso siamo in grado di srivere la matrice che rappresenta l'operatore $a$.
$$
	a=\begin{pmatrix}
	0 & \sqrt{ 1 }  & 0 & \cdot & \cdot & \cdot \\
	0 & 0 & \sqrt{ 2 } & \cdot & \cdot & \cdot \\
	0 & 0 & 0 & \sqrt{ 3 }  &  \cdot & \cdot \\
	\cdot & \cdot & \cdot & \cdot & \cdot & \cdot \\
	\cdot \\

	\end{pmatrix}
$$
$$
	a^{\dagger}=\begin{pmatrix}
	0 & 0 & 0 & 0 & \cdot & \cdot \\
	\sqrt{ 1 } & 0 & 0 & 0  & \cdot  & \cdot\\
	0 & \sqrt{ 2 } & 0 & 0  & \cdot & \cdot\\
	0 & 0 & \sqrt{ 3 } & \cdot & \cdot & \cdot
	\end{pmatrix}
$$
Ora posso trovare la matrice che rappresenta $\mathcal{H}$ e quelle che rappresentano $p$ e $x$:
$$
	\begin{cases}
	p=\sqrt{ \frac{m\hbar \omega}{2} } (a+a^{\dagger}) \\
	x= -i\sqrt{ \frac{\hbar}{2m\omega} }(a^{\dagger}-a)
	\end{cases}
$$
Entrambe hanno diagonale nulla, dunque:
$$
	\bra{n} p\ket{n} =\bra{n} x \ket{n} =0
$$
Che sono i valori medi di posizione e impulso che avevamo già trovato.
Posso fare la stessa cosa anche coi valori medi di $p^2$ e $x^2$.
$$
	p^2 = \frac{m\hbar \omega}{2} (a^2+(a^{\dagger})^2+2a^{\dagger}a+1)=\frac{m\hbar \omega}{2} (2n+1)=m\hbar \omega \left( n+\frac{1}{2} \right)
$$
Posso calcolare anche la funzione d'onda?
$$
	\psi_{n}(x)\equiv \braket{ x | n } 
$$

