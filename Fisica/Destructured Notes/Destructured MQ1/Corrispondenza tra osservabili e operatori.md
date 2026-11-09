
Il secondo postulato della meccanica quantistica è il seguente: tutte le osservabili fisiche $A_{S}=A_{S}(\{ q \}, \{ p \})$ del sistema $S$ sono rappresentate in $\mathcal{H}_{S}$ da OPERATORI LINEARI AUTOAGGIUNTI $\hat{A}$.
Questi operatori hanno equazioni agli autovalori:
$$
	\hat{A}\ket{a_{\sigma}} =a_{\sigma}\ket{a_{\sigma}} 
$$
Osservazioni varie:
- gli $a_{\sigma}$ possono formare uno spettro discreto $a_{\sigma}\in \mathbb{N}$ , oppure possono avere uno spettro continuo, ovvero $a_{\sigma}\in \mathbb{R}$.
- I corrispondenti autovettori $\ket{a_{\sigma}}$ formano basi ON (che supponiamo siano basi complete) in senso stretto nel caso discreto e basi ortogonali in senso generalizzato nel caso continuo $\implies$ $\{ \ket{a_{\sigma}} \}$ sono basi in $\mathcal{H}$.
- Interpreto $\{ a_{\sigma} \}$ come l'insieme dei possibili risultati per le misure di $A$.
- Gli stati $\ket{a_{\sigma}}$ sono stati nei quali una misura dell'osservabile $A$ è esattamente determinata, cioè fornisce sempre $a_{\sigma}$ con $P(a_{\sigma})=1$. Infatti:
$$
	\begin{aligned}
	\langle \hat{A} \rangle _{\sigma}&\equiv \bra{a_{\sigma}} \hat{A}\ket{a_{\sigma}} =a_{\sigma} \langle a_{\sigma}|a_{\sigma} \rangle =a_{\sigma}\\
	\langle \hat{A}^2 \rangle _{\sigma}&\equiv \bra{a_{\sigma}} \hat{A}^2\ket{a_{\sigma}} =a^2_{\sigma} \langle a_{\sigma}|a_{\sigma} \rangle =a_{\sigma}^2\\
	\implies&(\Delta \hat{A})_{\sigma}=\sqrt{ \langle \hat{A}^2 \rangle _{\sigma}-\langle \hat{A} \rangle _{\sigma}^2 }=0
	\end{aligned}
$$
- Gli autovalori $a_{\sigma}$ possono essere degeneri, cioè avere autospazi di dimensioni maggiori di 1.

**Lezione Associata:** [[6.Principi Fondativi della meccanica quantistica]]