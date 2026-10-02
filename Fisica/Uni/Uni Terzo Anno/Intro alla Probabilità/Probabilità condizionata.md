---
corso: Intro alla Probabilità
data: 2026-10-01
tags:
  - lezione
argomenti:
  - Probabilità
lezione-precedente: "[[Introduzione e concetti base di teoria della probabilità]]"
source:
---


> [!info] Contesto
> Corso: Intro alla probabilità
> Argomenti previsti: Probabilità condizionata, Formula di Bayes e conseguenze, casi applicativi di probabilità condizionata

## Riassunto veloce



## Appunti

In questa sezione ci occupiamo di come varia la probabilità di un evento sapendo che è avvenuto un altro evento.
$$
	P(A|B)\equiv \frac{P(A\cap B)}{P(B)}
$$
$=$ probabilità che avvenga $A$ sapendo che è avvenuto $B$.

Se gli eventi sono indipendenti abbiamo che $P(A\cap B)=P(A)P(B)$ dunque:
$$
	P(A|B)=\frac{P(A)P(B)}{P(B)}=P(A)
$$
Cioè se A e B sono indipendenti allora la probabilità che esca A non cambia sapendo che è uscito B.

#### Formula di Bayes
$$
	P(B|A)=P(A|B) \frac{P(B)}{P(A)} \,\left( = \frac{P(A\cap B)}{P(B)} \frac{P(B)}{P(A)} \equiv P(B|A) \right)
$$
La dimostrazione (banale) è quella illustrata tra le parentesi.

La formula di Bayes ha le seguenti conseguenze

- **Teorema della probabilità completa**
Consideriamo $\{ B_{i} \}^N_{i=1}$, partizione di $\Omega$.
$$
	\forall A \quad P(A)=\sum^N_{i=1}P(A|B_{i})P(B_{i})
$$
la dimostrazione è abbastanza chiara per via grafica, semplicemente vado a sommare la probabilità di $A\cap B_{i}$ fino a ottenere la probabilità di $A\cap \Omega \equiv A$:
![[Pasted image 20260930225935.png|439]]

- **Teorema delle moltiplicazioni**
$$
	P(A_{1}\cap A_{2}\cap\dots\cap A_{N})=P(A_{1})P(A_{2}|A_{1})P(A_{3}|A_{2}\cap A_{1})\dots P(A_{N}|A_{1}\cap A_{2}\cap\dots\cap A_{N-1})
$$
La dimostrazione si fa per induzione sfruttando la definizione di probabilità condizionata e la formula di Bayes.

Sfruttiamo il teorema delle moltiplicazioni per calcolare qual è il numero minimo di persone tale che la probabilità che 2 siano nati lo stesso giorno sia maggiore del $50\%$.




## Domande per revisione
- [ ] 

## Collegamenti
- Lezione precedente: [[Introduzione e concetti base di teoria della probabilità]]
- Concetti collegati: [[]]

