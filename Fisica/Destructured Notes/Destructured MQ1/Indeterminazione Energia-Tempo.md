
**Essenziale:** [[Derivazione delle relazioni di indeterminazione]], [[Teorema di Ehrenfest]]

Si può vedere anche:
$$
	\Delta E \cdot \Delta t \geq \frac{\hbar}{2}
$$
"più è piccola l'incertezza su $E$, più tempo ho per misurarla".
Ma ho un problema, $t$ non è un osservabile e non posso associarvi un operatore, allora come calcolo $\Delta t$?
In meccanica non relativistica non misuro mai il tempo, misuro sempre qualcosa ad un dato tempo, $t$ è un parametro.
Abbiamo sempre discusso di $\mathcal{H}$ ad un tempo fissato. Proviamo a rendere più chiaro il significato di questa disuguaglianza.

Per il teorema di Ehrenfest:

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

**Lezione associata:** [[6.Principi Fondativi della meccanica quantistica]]