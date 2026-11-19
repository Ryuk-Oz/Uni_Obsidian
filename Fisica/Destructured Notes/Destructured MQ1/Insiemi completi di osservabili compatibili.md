**Utile:** [[Commutatori e relazioni di indeterminazione]]

- Dato un set di osservabili $\{ a_{i} \}$, $i=1,\dots,p$; si dice che le osservabili sono COMPATIBILI se i corrispondenti operatori commutano (sono cioè simultaneamente misurabili).
$$
	[A_{i},A_{j}]=0 \qquad \forall i,j=1,\dots,p
$$
- Diciamo che $a$ e $b$ sono INDIPENDENTI se la misura di una di esse non determina il risultato di una misura dell'altra. (si tratta di una definizione di indipendenza diversa da quella che si dà in teoria delle probabilità)
  Se due osservabili sono compatibili e indipendenti $\implies$ ci deve essere degenerazione. Il motivo sta ne fatto che le 2 osservabili condividono gli autostati; se entrambi fossero non degeneri allora l'autovalore di $A$ coinciderebbe sempre con l'autovalore di $B$ (quindi coinciderebbero le 2 misurazioni) e le 2 osservabili NON sarebbero indipendenti.
  $\exists$ diversi stati $\ket{a_{i}, \cdot}\in$ autovalori diversi di $B$.
  Dunque non ha più senso chiamare lo stato $\ket{a_{i}}$, ma è meglio usare una notazione di questo tipo:
  $\ket{a_{i}}\to\ket{a_{i},b_{i}} \, /\, \begin{cases}A\ket{a_i, b_{j}} =a_{i}\ket{{a_{i}, b_{j}}} \\  B\ket{{a_{i}, b_{j}}}=b_{j} \ket{{a_{i}, b_{j}}}\end{cases}$
- Dato un sistema fisico $S$ gli stati di $\mathcal{H}_{S}$ sono completamente caratterizzati quando ho misurato $p$ osservabili complete e indipendenti e **tali da rimuovere la degenerazione**.
  In questo caso dico di avere un ICOC.

**Lezione Associata:** [[6.Principi Fondativi della meccanica quantistica]]