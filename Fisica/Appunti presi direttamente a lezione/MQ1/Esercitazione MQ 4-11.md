
### Esercizi sull'oscillatore armonico

Recap equazioni utili:
$$
	\begin{aligned}
	\hat{H}&=\frac{\hat{p}^2}{2m}+\frac{1}{2}k \hat{x}^2,\quad k=m\omega^2\\
	&=\hbar \omega\left( \hat{a}^{\dagger}\hat{a}+\frac{1}{2} \right)
	\end{aligned}
$$
con gli operatori di creazione $\hat{a}^{\dagger}$ e distruzione $\hat{a}$:
$$
	\begin{aligned}
	\hat{a}^{\dagger}= \frac{1}{\sqrt{ 2m\omega \hbar }}(\hat{p}+im\omega \hat{x})\\
	\hat{a}=\frac{1}{\sqrt{ 2m\omega \hbar }}(\hat{p}-im\omega \hat{x})
	\end{aligned}
$$
Con annesse relazioni di commutazione:
$$
	[\hat{x},\hat{p}]=i\hbar, \qquad [\hat{a},\hat{a}^{\dagger}]=1
$$
riscriviamo gli operatori $\hat{x}$ e $\hat{p}$ in funzione degli operatori di creazione e distruzione:
$$
	\begin{cases}
	\hat{x}=i \sqrt{ \frac{\hbar}{2} } \frac{1}{\sqrt{ m\omega }}(\hat{a}-\hat{a}^{\dagger}) \\
	\hat{p}=\sqrt{ \frac{\hbar}{2} } \sqrt{ m\omega }(\hat{a}+\hat{a}^{\dagger})
	\end{cases}
$$
Da tutto questo è possibile ottenere lo spettro di energia:
$$
	\hat{H} \ket{n}=E_{n}\ket{n} 
$$
con:
$$
	\begin{aligned}
	&E_{n}=\hbar \omega\left( n+\frac{1}{2} \right)\\
	&\hat{a}^{\dagger}\ket{n} =\sqrt{ n+1 }\ket{n+1}\\
	&\hat{a} \ket{n} =\sqrt{ n }\ket{n-1} \\
	 &\hat{N}=\hat{a}^{\dagger}\hat{a}, \quad \hat{N}\ket{n} =n\ket{n} 
	\end{aligned}
$$

**Esercizio 1** (Griffiths 3.35)

1. Usando il metodo algebrico di Heisenberg mostra che gli autostati dell'energia $\ket{n}$ soddisfano: 
   $$
   	\sigma_{x}\sigma_{p}=\underbrace{(2n+1) \frac{\hbar}{2}}_{\geq \frac{\hbar}{2}}
   $$
**Soluzione:**
$$
	\begin{aligned}
	&\sigma_{x}=\sqrt{ \langle \hat{x}^2 \rangle -\langle \hat{x} \rangle ^2 } \\
	&\langle \hat{x} \rangle _{n} = \bra{n} \hat{x}\ket{n} =0
	\end{aligned}
$$
perchè:
$$
	\begin{aligned}
	\bra{n} \hat{x}\ket{n} &= \bra{n} i \sqrt{ \frac{\hbar}{2} } \frac{1}{\sqrt{ m\omega }}(\hat{a}-\hat{a}^{\dagger}) \ket{n} \\
	&=i\sqrt{ \frac{\hbar}{2} \frac{1}{m\omega} }(\bra{n} \sqrt{ n }\ket{n-1} -\bra{n}\sqrt{ n+1 }\ket{n+1}  )
	\end{aligned}
$$
e $\braket{ n | m }=\delta_{nm}\implies \langle \hat{x} \rangle_{n}=0$
In modo analogo troviamo $\langle \hat{p} \rangle_{n}=0$.
$$
  \begin{aligned}
  	\langle \hat{x}^2 \rangle _{n}&= \bra{n}  \left( -\frac{\hbar}{2} \frac{1}{m\omega} \right)(\hat{a}^2+\hat{a}^{\dagger \,2} -\hat{a}\hat{a}^{\dagger}-\hat{a}^{\dagger}\hat{a})\ket{n} \\
  	&=\frac{\hbar}{2} \frac{1}{m\omega} \bra{n} \hat{a}\hat{a}^{\dagger}+\hat{a}^{\dagger}\hat{a}\ket{n} 
  \end{aligned}
$$
Ora:
$$
	\begin{cases}
	\hat{a}^{\dagger}\hat{a}\ket{n} = \sqrt{ n }\hat{a}^{\dagger}\ket{n-1} =\sqrt{ n }\sqrt{ n }\ket{n} =n\ket{n} \\
	\hat{a}\hat{a}^{\dagger} \ket{n} =\sqrt{ n+1 }\hat{a}\ket{n+1} =(n+1)\ket{n+1} 
	\end{cases}
$$
Dunque:
$$
	\langle \hat{x}^2 \rangle _{n}=\frac{\hbar}{2} \frac{1}{m\omega} (2n+1)
$$
Analogamente per $\langle \hat{p}^2 \rangle$ ho:
$$
	\langle \hat{p}^2 \rangle _{n}= \frac{\hbar}{2} m\omega (2n+1)
$$
Alla fine arrivo a trovare:
$$
	\begin{aligned}
	&\sigma_{x}=\sqrt{ \frac{\hbar}{2} \frac{1}{m\omega} }\sqrt{ 2n+1 }\\
	&\sigma_{p}=\sqrt{ \frac{\hbar}{2}m\omega }\sqrt{ 2n+1 }
	\end{aligned}
$$
E trovo: 
$$
	\sigma_{x}\sigma_{p}= \frac{\hbar}{2}(2n+1)
$$

2. Consideriamo uno stato $\ket{\alpha}$ che è un autostato di $\hat{a}$.
$$
	\hat{a}\ket{\alpha} =\alpha \ket{\alpha} 
   $$
   dove $\alpha \in \mathbb{C}$, $\braket{ \alpha | \alpha }=1$
- Calcolare i valori medi di $\hat{x},\hat{p},\hat{x}^2,\hat{p}^2$ per lo stato $\alpha$
- Mostrare che $\sigma_{x}\sigma_{p}=\frac{\hbar}{2}$, minimo della relazione di indeterminazione
- Scriviamo $\ket{ \alpha}$ nella base di $\ket{n}$:
$$
	\ket{\alpha} =\sum_{n}^\infty c_{n} \ket{n} 
   $$
   e mostra che i coefficienti sono:
   $$
	c_{n}= \frac{\alpha^n}{\sqrt{ n! }}c_{0}
   $$
- usando $\braket{ \alpha | \alpha }=1$, mostra che:
$$
	c_{0}=\exp\left( - \frac{|\alpha|^2}{2} \right)
   $$
- per un tempo $t>0$ mostrare che $\ket{\alpha(t)}$ e anche un'autostato di $\hat{a}$,
  con autovalore $\alpha(t)=\alpha e^{ -i\omega t }$:
$$
	\hat{a} \ket{\alpha(t)} =\alpha(t) \ket{\alpha(t)} 
$$
**Soluzione:**

PRIMO e SECONDO PUNTO:
$$
	\begin{aligned}
	\langle \hat{x} \rangle _{\alpha}&= \bra{\alpha} i \sqrt{ \frac{\hbar}{2} } \frac{1}{\sqrt{ m\omega }}(\hat{a}-\hat{a}^{\dagger})\ket{\alpha}\\
	&=i \sqrt{ \frac{\hbar}{2} } \frac{1}{\sqrt{ m\omega }} (\alpha-\alpha^*)
	\end{aligned} 
$$
NOTA: $(\bra{\alpha}\hat{a}^{\dagger}=\bra{\alpha}\alpha^*)$ 
Se $\alpha= \mathrm{Re}(\alpha)+i\mathrm{Im}(\alpha)$, posso scrivere:
$$
	\langle \hat{x} \rangle _{\alpha}= -\sqrt{ \frac{\hbar}{2} } \frac{1}{\sqrt{ m\omega }} 2 \mathrm{Im}(\alpha)
$$
$$
	\begin{aligned}
	\langle \hat{p} \rangle _{\alpha}= \bra{\alpha}  \sqrt{ \frac{\hbar}{2} } \sqrt{  m\omega } (\hat{a}+\hat{a}^{\dagger})\ket{\alpha} = \sqrt{ \frac{\hbar}{2} m\omega }(\alpha+\alpha^*) = 2\sqrt{ \frac{\hbar}{2}m\omega }\; \mathrm{Re}(\alpha)
	\end{aligned}
$$
Procediamo con il calcolo dei momenti quadri.
$$
	\begin{aligned}
	\langle \hat{x}^2 \rangle _{\alpha} &= -\frac{\hbar}{2} \frac{1}{m\omega} \bra{\alpha} (\hat{a}^2+\hat{a}^{\dagger\,2}-\hat{a}\hat{a}^{\dagger}-\hat{a}^{\dagger}\hat{a})\ket{\alpha} \\
	&= -\frac{\hbar}{2} \frac{1}{m\omega} \bra{\alpha} (\hat{\alpha}^2+\hat{\alpha}^{\dagger\, 2}-2\hat{a}^{\dagger}\hat{a}-[\hat{a}, \hat{a}^{\dagger}])\ket{\alpha} \\
	&=-\frac{\hbar}{2} \frac{1}{m\omega} (\alpha^2 +\alpha^{*2}-2 \alpha \alpha^*-1)=\frac{\hbar}{2} \frac{1}{m\omega} (4\mathrm{Im}(\alpha)^2+1)
	\end{aligned}
$$
Il calcolo di $\langle \hat{p}^2 \rangle_{\alpha}$ è analogo:
$$
	\langle \hat{p}^2 \rangle _{\alpha}= \frac{\hbar}{2} m\omega (4\mathrm{Re}(\alpha)^2+1)
$$
Ora possiamo calcolare le varianze:
$$
	\begin{cases}
	\Delta_{\alpha}x^2 = \langle \hat{x}^2\ \rangle _{\alpha}-\langle \hat{x} \rangle ^2_{\alpha}= \frac{\hbar}{2} \frac{1}{m\omega} \\
	\Delta_{\alpha}p^2 = \frac{\hbar}{2} m\omega
	\end{cases}
$$
$\implies \sigma_{x}\sigma_{p}=\frac{\hbar}{2}$


TERZO PUNTO:

Sappiamo che:
$$
	\braket{ n | \alpha } =c_{n} 
$$
Sfruttando l'equazione agli autovalori di $\ket{a^{\dagger}}$ e andando a iterare possiamo ottenere:
$$
	\ket{n} = \frac{1}{\sqrt{ n! }} (\hat{a}^{\dagger})^n \ket{0} 
$$
$$
	\implies c_{n}= \frac{1}{\sqrt{ n! }} \bra{0} \hat{a}^n \ket{\alpha} = \frac{\alpha^n}{\sqrt{ n! }} \braket{ 0 | n } =\frac{\alpha^n}{\sqrt{ n! }} c_{0} 
$$
QUARTO PUNTO:
$$
	\braket{ \alpha | \alpha } =1
$$
$$
	\implies \left( \sum_{n} c_{n}^* \bra{n}  \right)\left( \sum_{m} c_{m} \ket{m}  \right) = \sum_{n} |c_{n}|^2 =1
$$
Dunque:
$$
	|c_{0}|^2 \sum_{n} \frac{|\alpha|^{2n}}{n!}=1\implies |c_{0}|^2 e^{ |\alpha|^2 }=1
$$
Da cui:
$$
	c_{0}= \exp\left( -\frac{|\alpha|^2}{2} \right)
$$
 QUINTO PUNTO:
$$
\ket{n(t)}=\exp\left( -\frac{i}{\hbar} E_{n} t \right)\ket{n}  
$$
Allora:
$$
	\ket{\alpha(t)} = \sum^\infty_{n=0} c_{n} \exp\left( -\frac{i}{\hbar} E_{n}t \right) \ket{n}  
$$
$$
    \begin{aligned}
	\hat{\alpha} \ket{\alpha(t)}  &= \sum^\infty_{n=0} c_{n} \exp\left( -\frac{i}{\hbar} E_{n}t \right) \hat{a}\ket{n} \\
	&= \sum c_{n} \exp\left( -\frac{i}{\hbar} E_{n}t \right) \sqrt{ n } \ket{n-1} \\
	&= \sum c_{n+1} \exp\left( -\frac{i}{\hbar} E_{n+1}t \right) \sqrt{ n+1 } \ket{n} 
	\end{aligned}
$$
Ora ricordiamo $c_{n+1}= \frac{\alpha}{n+1} c_{n}$ e $E_{n+1}=E_{n}+\hbar \omega$.
$$
	\implies \hat{\alpha} \ket{\alpha(t)}  = \sum \alpha c_{n} \exp\left( -\frac{i}{\hbar} E_{n}t-i\omega t \right)\ket{n}  = \alpha \exp(-i\omega t) \ket{\alpha(t)} 
$$
Uno stato con questa proprietà di chiama uno stato COERENTE.
Non ho un allargamento del pacchetto d'onda nel tempo.

**Esercizio 2:** (Esame del 8-7-24)
Un'oscillatore armonico è descritto dall'Hamiltoniana:
$$
	H=\frac{1}{2m}l^2 +\frac{1}{2}kx^2
$$
dove $k=m\omega^2$.
- Determina le coordinate di confini della regione di oscillazione consentita per il sistema classico, in termini della sua energia totale $E$.
- Se il sistema quantistico si trova nello stato di minima energia , determinare la probabilità di trovare la particella fuori dalla regione classicamente permessa
**Formule utili fornite all'esame:**
Autofunzione dell'energia: 
$$
		\varphi_{n}(x)=\left( \frac{m\omega}{\pi \hbar} \right)^{1/4} \frac{1}{\sqrt{ 2^n n!}} H_{n}(\xi) \exp\left( -\frac{\xi^2}{2} \right)
	$$
Con $\xi= \sqrt{ \frac{m\omega}{\hbar} }x$ e $H_{0}(x)=1$ e $H_{1}(x)=2x$.
Definiamo:
$$
	erf(y)= \frac{2}{\sqrt{ \pi }} \int_{0}^y dx\, e^{ -x^2 }
$$

SOLUZIONE:

risolviamo il PRIMO PUNTO:

l'energia cinetica a $x=x_{max}$ è nulla.
$$
	E=\frac{1}{2m}p^2 +\frac{1}{2} k x^2 = \frac{1}{2} kx_{max}^2
$$
Dunque $x_{max}=\pm \sqrt{ \frac{2E}{k} }=\pm \sqrt{ \frac{2E}{m\omega^2} }$

risolviamo il SECONDO PUNTO:

Lo stato di minima energia è $E_{0}=\hbar \omega$
Allora $x_{max}=\pm \sqrt{ \frac{2\hbar}{m\omega} }$.
L'autofunzione dell'energia è:
$$
	\varphi_{0}(x)=\left( \frac{m\omega}{\pi \hbar} \right)^{1/4} \exp\left( -\frac{m\omega x^2}{2\hbar} \right)
	
$$
La probabilità di trovare la particella fuori dalla regione classica $|x|>|x_{max}|$ è:
$$
\begin{aligned}
	p&= 2 \int^\infty_{|x_{max}|} |\varphi_{0}|^2 dx =1-2\int_{0}^{|x_{max}|} |\varphi_{0}|^2 dx\\
	&= 1-2 \int^{|x_{max}|}_{0} \sqrt{ \frac{m\omega}{x\hbar} } \exp\left( -\frac{m\omega}{\hbar}x^2 \right)= 1-2\int^1_{0} \frac{1}{\sqrt{ \pi }} dy \exp(-y^2)=1-2erf(1)
\end{aligned}
$$


