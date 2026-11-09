
**Per approfondire il legame tra separabilità e preparazione dello stato:** [[Interpretazione statistica generalizzata]]

Partiamo dal primo postulato: dato un sistema $S$, gli stati possibili per $S$ sono in corrispondenza biunivoca con i "raggi" di uno spazio di Hilbert $\mathcal{H}_{S}$ su $\mathbb{C}$.
Per arrivare a tale conclusione facciamo alcune ipotesi:
- Supponiamo che $\mathcal{H}_{S}$ sia SEPARABILE e COMPLETO.
  Voglio che lo spazio $\mathcal{H}_{s}$ sia separabile per poter fisicamente costruire uno stato in laboratorio (nel caso di basi non  numerabili avreio bisogno di una quantità di misure infinite per caratterizzare univocamente lo stato del mio sistema durante la sua preparazione).
  Voglio che $\mathcal{H}_{S}$ sia completo per poter scrivere ogni stato come una combinazione lineare "infinita" d vettori appartenenti a una base $\ket{n}$ senza uscire mai dal mio spazio $\mathcal{H}_{S}$.
- Se lo spazio delle configurazioni di $S$ è un volume $V_{S}$, con $\mathbb{R}^{3n}$ , allora $\mathcal{H}_{S}$ è isomorfo a $L^2(V_{S})$.
- I RAGGI in $\mathcal{H}_{S}$ sono classi di equivalenza di vettori, cioè posso modulare la norma e la fase di ogni stato $\ket{\alpha}$ senza cambiare lo stato fisico: 
$$
  	\ket{\alpha}  \sim k \ket{\alpha} \sim e^{ i\theta } \ket{\alpha} 
  $$
  L'insieme di tutti i vettori $\ket{\alpha}$, cioè l'insieme degli stati possibili è lo spazio di Hilbert quozientato con l'insieme dei numeri complessi:
$$
 \bar{\mathcal{H}}_{S}\equiv \{ \ket{\alpha}  \} \equiv \frac{\mathcal{H}_{S}}{\mathbb{C}}
$$
- Una possibile rappresentazione dello stato fisico è la sua FUNZIONE D'ONDA in $V_{S}$
$$
	\langle \vec{r}|\alpha \rangle \equiv \psi_{\alpha}(\vec{r})
  $$
  Ma devo essere più preciso nello stabilire cosa caratterizza uno stato in modo univoco
- Lo spazio $\mathcal{H}_{S}$ (e quindi lo spazio $\bar{\mathcal{H}}_{S}$) è lo spazio degli stati a TEMPO FISSATO. L'evoluzione temporale è dettata dall'EdS.
  L'EdS può essere riscritta in $\mathcal{H}$ nel seguente modo:
>[!abstract] Equazione di Shrödinger scritta tramite operatori:
>
>$$
>	i\hbar \frac{d}{dt} \ket{\alpha(t)} =\hat{H} \ket{\alpha(t)} 
>$$


**Lezione Associata:** [[6.Principi Fondativi della meccanica quantistica]]