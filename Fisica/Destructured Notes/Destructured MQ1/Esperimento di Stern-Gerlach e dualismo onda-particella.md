
**Per un po' di contesto ulteriore:** [[Spettroscopia e modelli atomici]]

L'obiettivo è quello di andare a verificare sperimentalmente la quantizzazione del momento angolare. Per farlo, si utilizzano degli atomi neutri (Ag) che vengono fatti deviare da un campo magnetico, per via del momento magnetico degli atomi.

![[Pasted image 20260927231221.png]]

$$
	\begin{aligned}
	U &= - \vec{\mu}\cdot \vec{B} \\
	\Rightarrow F_{z} &= \mu_{z}\frac{ \partial B_{z} }{ \partial z } \\ 
	\end{aligned}
$$
da cui otteniamo, ricodando la relazione che avevamo ottenuto nell'atomo di Bohr:
$$
	\vec{\mu}\propto \vec{L}
$$
Classicamente mi aspetto che la direzione di $\vec{\mu}$ sia casuale e sullo schermo compaia una distribuzione simile a un $\cos x$, invece ottengo una serie di picchi isolati ed equidistanti (nel caso dell'argento ho 2 picchi).

![[Pasted image 20260927231654.png]]

Come vado ad interpretare questi risultati sperimentali?
- Ho la conferma che $L_{z}$ sia quantizzato, inoltre ruotando l'apparato sperimentale ottengo gli stessi risultati sulle proiezioni di $L$, da cui capisco che l'invarianza per rotazione è conservata.
- Dall'invarianza per rotazione capisco che $\vec{L}$ non può essere un vettore nel senso classico del termine
Infine, mettendo più apparati in serie, si osserva qualcosa di incredibilmente interessante. Se divido il fascio in 2 in una direzione, poi scelgo uno dei due fasci e lo faccio passare per 2 magneti ruotati dividendo nuovamente il fascio in 2, ed infine, ne scelgo nuovamente uno e lo faccio passare per altri magneti orientati nel modo originale, vado ad osservare nuovamente una separazione del fascio. Questo significa che la seconda misura ha "distrutto" la vecchia misura del momento angolare.

Vedremo poi che questo esperimento non stava davvero misurando il momento angolare, bensì lo spin dell'atomo.

#### Ipotesi di De Broglie, dualismo onda-particella (~1924)

Nel 1924, viene proposta una nuova ipotesi rivoluzionaria per chiarire ulteriormente il modello di Bohr.
Sappiamo che per la luce vale:
$$
	pc =E=h\nu=\hbar \omega \Rightarrow p=\frac{h}{\lambda}=\hbar k
$$
per particelle di materia non relativistiche sappiamo invece che:
$$
	p=mv
$$
immaginiamo adesso di poter adattare quello che vale per la luce anche ad altre particelle di materia (questa è l'ipotesi di de Broglie):
$$
	p=mv=\frac{h}{\lambda}
$$
sotto l'ipotesi di Bohr sappiamo che:
$$
	2\pi L_{z}=2\pi mvr=p\mathcal{L}=\frac{h}{\lambda}\mathcal{L}=nh
$$
dove $\mathcal{L}$ è la lunghezza dell'orbita.
Così otteniamo:
$$
	\mathcal{L}=n\lambda
$$
Applicandolo all'elettrone, questo significa che all'$e^{-}$ associamo un'onda le cui orbite stazionarie sono quelle in cui l'onda che gli abbiamo associato è stazionaria. Laddove questa condizione fallisse, ho un fenomeno di autointerferenza distruttiva e l'orbita sarebbe instabile (o non esisterebbe proprio).

![[Pasted image 20260927233548.png|278]]

L'eleganza di quest'ipotesi, al di là del fatto che spiegherebbe l'ipotesi di Bohr, sta nell'aver ristabilito una simmetria tra radiazione elettromagnetica (luce) e materia.
Quale sarebbe la lunghezza d'onda dell'elettrone?
Per una differenza di potenziale di circa $100\text{V}$ otteniamo un energia di circa $10^{-17}$ Joule che equivale a $\lambda \sim {10}^{-10} \text{m}$.
Nel caso in cui questa ipotesi fosse verificata sperimentalmente, ci mancherebbero però 2 cose:
- un interpretazione
- un'equazione d'onda


**Lezione associata:** [[1.Introduzione storica alla meccanica quantistica]]