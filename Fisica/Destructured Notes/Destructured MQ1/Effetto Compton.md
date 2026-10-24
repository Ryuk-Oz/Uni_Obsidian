L'effetto Compton descrive il processo d'urto tra un $e^-$ e della radiazione elettromagnetica (raggi x). Anche in questo caso sorgono dei problemi nella descrizione classica del fenomeno ed è necessario andare ad introdurre una quantizzazione.

![[Pasted image 20260924141007.png]]

Per risolvere il problema classicamente, vado a risolvere le equazioni di Maxwell con opportune condizioni al contorno. Così facendo trovo che $\lambda$ della radiazione non cambia dopo l'urto ed è indipendente dall'angolo $\theta$. Tuttavia entrambe queste affermazioni sono in disaccordo con i risultati sperimentali.

Introduciamo dunque la quantizzazione e immaginiamo l'onda come se fosse fatta di tanti pacchetti (quantizzati) dotati di un'energia e un impulso (i fotoni).
Adesso modelliamo l'urto come un urto tra particelle relativistiche.

![[Pasted image 20260924141326.png]]

scriviamo il quadrimpulso delle particelle:
$$p^\mu=\left( \frac{E}{c}, \vec{p} \right)$$.
Sappiamo che l'energia del fotone è $E_{\gamma}=h\nu$ e la sua massa è $m_{\gamma}=0$. Applicando mass-shell si trova:
$$
	(h\nu)^2=|\vec{p}|^2 c^2 \Rightarrow |\vec{p}|=\frac{h\nu}{c}=\frac{h}{\lambda}
$$
cioè anche l'impulso del fotone è quantizzato.
Per l'elettrone ho invece:
$$
	E_{e}=\sqrt{ |p_{e}|^2c^2+m_{e}^2c^2 }
$$
Studiamo l'urto imponendo la conservazione del quadrimpulso:
$$
	\begin{cases}
	E_{\gamma}+E_{e}= E'_{\gamma}+E'_{e} \\ \\
	\vec{p}_{\gamma}+\vec{p}_{e}=\vec{p}'_{\gamma}+\vec{p}'_{e}
	\end{cases}
$$
scelgo il sistema a targhetta fissa in cui l'elettrone è a riposo.
$$
	\begin{cases}
	E_{\gamma}+m_{e}c^2=E_{\gamma}'+E_{e}' \\
	\vec{p}_{\gamma}=\vec{p}'_{\gamma}+\vec{p}'_{e}
	\end{cases}
$$
$$
\begin{aligned}
	E_{\gamma}-E'_{\gamma}+m_{e}c^2&=E_{e}' = \sqrt{ m_{e}^2c^4+|\vec{p}_{e}|^2 c^2 }=\sqrt{ m_{e}c^4+|\vec{p}_{\gamma}-\vec{p}_{\gamma}'|^2c^2 } \\
	&=\sqrt{ m_{e}^2 c^4+|\vec{p}_{\gamma}|^2 c^2+|\vec{p}'_{\gamma}|c^2-2|\vec{p}_{\gamma}||\vec{p}_{\gamma}'|\cos^2\theta c^2 }\\
	&=\sqrt{ m_{e}^2c^2 +E_{\gamma}^2+E'^2_{\gamma}-2E_{\gamma}E'_{\gamma}\cos \theta c^2}
\end{aligned}
$$
elevo tutto al quadrato:
$$
	(E_{\gamma}+E'_{\gamma}+m_{e}c^2)^2= m_{e}^2c^2 +E_{\gamma}^2+E'^2_{\gamma}-2E_{\gamma}E'_{\gamma}\cos \theta c^2
$$
andando a sviluppare il quadrato a sinistra e semplificando otteniamo:
$$
	m_{e}c^2(E_{\gamma}-E_{\gamma}')-E_{\gamma}E'_{\gamma}=-E_{\gamma}E_{\gamma}'\cos \theta
$$
andando a sostituire $E=h\nu$:
$$
	\begin{aligned}
	m_{e}c^2\left( \frac{hc}{\lambda}-\frac{hc}{\lambda'} \right)-\frac{h^2c^2}{\lambda \lambda'}&=-\frac{h^2c^2}{\lambda \lambda'}\cos \theta \\
	\Rightarrow \lambda'-\lambda&=\frac{h}{m_{e}c}(1-\cos \theta)
	\end{aligned}
$$
Abbiamo ottenuto la formula dell'effetto Compton, che contraddice totalmente i calcoli classici in quanto $\lambda'$ non solo differisce da $\lambda$ ma varia anche con $\theta$.

Questa formula ci permette anche di introdurre la lunghezza d'onda Compton (dell'elettrone):
$$
	\lambda_{c}=\frac{h}{m_{e}c}
$$
che equivale alla lunghezza d'onda di un fotone che ha come energia l'energia a riposo dell'$e^-$.
Analogamente posso definire la lunghezza d'onda Compton di varie particelle differenti.


**Lezione associata:** [[1.Introduzione storica alla meccanica quantistica]]