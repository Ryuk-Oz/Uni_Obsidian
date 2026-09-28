---
corso: Metodi 2
data: 2026-09-28
tags:
  - lezione
argomenti: []
lezione-precedente: "[[Mappe conformi e Continuazione Analitica]]"
source:
---


> [!info] Contesto
> Corso: metodi 2
> Argomenti previsti: 

## Riassunto veloce



## Appunti

Iniziamo adesso lo studio di un grande gruppo di funzioni "patologiche", le funzioni polidrome.

Per farlo partiamo dallo studio di un esempio semplice:
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
La linea di discontinuità prende  il nome di **taglio** e i punti che giacciono sulla linea sono detti **punti di diramazione**.

Cerchiamo una soluzione a questo problema. Proviamo a definire l'inversa andando ad utilizzare più fogli. Quello che otterremo è una funzione continua in cui il valore sul taglio di un foglio arrivando "dal basso" è uguale al valore sul secondo foglio arrivando "dall'alto", questo ci permette di "incollare" i fogli e andare a definire una funzione il cui dominio passa da un foglio all'altro in corrispondenza dei punti di diramazione. In questa sezione ci occuperemo di formalizzare più efficacemnete questa idea andando a studiare le funzioni cosìdette **polidrome**.

La seguente immagine da una buona idea di quello che andiamo a operare sul dominio.
![[Pasted image 20260929000847.png]]



## Domande per revisione
- [ ] 

## Collegamenti
- Lezione precedente: [[Mappe conformi e Continuazione Analitica]]
- Concetti collegati: [[]]

