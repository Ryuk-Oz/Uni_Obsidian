
**Utili:** [[Proprietà dei polinomi di Hermite]], [[Azione degli operatori gradino sugli autostati dell'Hamiltoniana]]

Vogliamo studiare le funzioni d'onda $\psi_{n}(x)$ dell'oscillatore armonico.
Sappiamo cosa vogliamo calcolare:
$$
	\psi_{n}(x)=\braket{ x | n }   
$$
Normalizziamo gli stati $\ket{n}$.
$$
	\ket{0} : a\ket{0} =0, \quad \ket{1} = N_{1} a^{\dagger} \ket{0}  
$$
$$
	\braket{ 1 | 1 } =1= N_{1} \bra{1} a^{\dagger}\ket{0} =N_{1} \sqrt{ 1}\implies N_{1}=1 
$$
Studiamo gli stati successivi:
$$
	\ket{2} = N_{2} (a^{\dagger})^2 \ket{0} 
$$
Imponiamo la normalizzazione:
$$
	1=\braket{ 2 | 2 } = N_{2} \bra{2} (a^{\dagger})^2\ket{0} =N_{2} \bra{2} a^{\dagger}\ket{1} \bra{1} a^{\dagger}\ket{0} =N_{2} \sqrt{ 2 }\sqrt{ 1 }\implies N_{2}=\frac{1}{\sqrt{ 2\cdot{1} }} 
$$
Generalizzando al caso $n$-esimo troviamo:
$$
	N_{n}=\frac{1}{\sqrt{ n! }}
$$
Dunque:
$$
	\ket{n} = \frac{(a^{\dagger})^n}{\sqrt{ n! }} \ket{0} 
$$
Lo stato $\ket{0}$ è normalizzato per definizione.

Ricaviamo ora le funzioni d'onda, partendo dallo stato fondamentale.
$$
	a\ket{0} =0 \implies (p-im\omega x)\ket{0} =0
$$
$$
	\begin{aligned}
	0&=\bra{x} p-im\omega x\ket{0}=\int dy\, \bra{x} p \ket{y} \braket{ y | 0 }-im\omega x\underbrace{\braket{ x | 0 } }_{\psi_{0}(x)}\\
	&=\int dy\, \delta(x-y)\left( -i\hbar \frac{d}{dy} \right) \psi_{0}(y)-im\omega x \psi_{0}(x) =\left( -i\hbar \frac{d}{dx} \right) \psi_{0}(x)-im\omega x \psi_{0}(x)=0
	\end{aligned}
$$
Mi sono ricondotto ad un'equazione differenziale banale.
$$
	\frac{d\psi_{0}(x)}{dx}= -\frac{m\omega}{\hbar} x\psi_{0}(x)\implies \psi_{0}(x)=Ne^{ -1/2\; \frac{m\omega}{\hbar} x^2 }
$$
Chiamando $\sqrt{ \frac{m\omega}{\hbar} }=\alpha$ e normalizzando otteniamo:
$$
	\psi_{0}(x)= \sqrt{ \frac{\alpha}{\sqrt{ \pi }} } e^{  -1/2 \; \alpha^2 x^2}
$$
A questo punto troviamo $\psi_{n}$:
$$
	\psi_{n}=\braket{ x | n } = \frac{1}{\sqrt{ n! }} \frac{1}{(2m\hbar \omega)^{n/2}}\left( -i\hbar \frac{d}{dx}+im\omega x \right)^n \psi_{0}(x)
$$
Definisco $\xi=\alpha x=\sqrt{ \frac{m\omega}{\hbar} }x$.
$$
	\begin{aligned}
	\psi_{n}(\xi)&= \frac{1}{\sqrt{ n! }} \frac{1}{(2m\hbar \omega)^{n/2}}\left( -i\hbar \sqrt{ \frac{m\omega}{\hbar} } \frac{d}{d\xi}+im\omega \sqrt{ \frac{\hbar}{m\omega} }\xi \right)^n \psi_{0}(\xi)\\
	&=\sqrt{ \frac{\alpha}{2^n n! \sqrt{ \pi }} }(-i)^{n} \left( \frac{d}{d\xi}-\xi \right)^n e^{ -1/2\; \xi^2 }
	\end{aligned}
$$
Questa è un'altra versione della formula di Rodriguez! $\implies$ escono i polinomi di Hermite
**OSS**:
$$
	\left( \frac{d}{d\xi}-\xi \right)^n f(\xi) = \left( e^{ 1/2 \; \xi^2 } \frac{d^n}{d\xi^n} e^{ -1/2 \; \xi^2 } \right) f(\xi)
$$
Si verifica per induzione.

Sostituendo nel risultato di prima troviamo:
$$
	\psi_{n}(\xi)=N_{n} i^n e^{ -1/2\; \xi^2 }\left[ (-1)^n e^{ \xi^2 } \frac{d^n}{d\xi^n} e^{ -\xi^2 } \right] = i^n \psi_{n}^{\text{ricavati da Shrö}}(\alpha x)
$$
Abbiamo ritrovato le stesse funzioni d'onda che si otterrebbero con l'equazione di Shrödinger, moltiplicati per una fase $(i)^n$ ...MA... non ci interessa perchè sappiamo che gli stati sono gli stessi a meno di una fase e di un fattore di scala.

**Lezione Associata:** [[7. Oscillatore armonico quantistico (con la teoria degli operatori)]]