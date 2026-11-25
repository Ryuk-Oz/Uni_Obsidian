
**Essenziale:** [[Limiti energetici dell'oscillatore armonico con il formalismo dei bra e dei ket]]

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
Preso un qualunque stato $\ket{l}$ posso considerare un nuovo stato $a^{\dagger}\ket{l}$. Cosa so sull'energia di questo nuovo stato? Per studiarlo ci faccio agire sopra l'Hamiltoniana:
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
	\varepsilon_{n}=\left( n+\frac{1}{2} \right) \implies E_{n}=\left( n+\frac{1}{2} \right)\hbar \omega
$$

**Lezione associata:** [[7. Oscillatore armonico quantistico (con la teoria degli operatori)]]