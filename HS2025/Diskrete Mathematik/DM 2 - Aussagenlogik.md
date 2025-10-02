#HS2025 #DM 

## Bausteine der Aussagenlogik

- Symbole: $(A,B,C, \dots)$, können Werte $0,1$ annehmen
- Operatoren: $\neg, \land, \lor, \implies, \iff$, operieren auf Symbolen und Formeln
- Formeln: (geklammerte) Ausdrücke von Operatoren und Symbolen

| A   | B   | $\neg A$ | $A\land B$ | $A\lor B$ | $A\implies B$ | $A\iff B$ | $\neg A\lor B$ | $(\neg A\lor B)\land(A\implies B)$ |     |
| --- | --- | -------- | ---------- | --------- | ------------- | --------- | -------------- | ---------------------------------- | --- |
| 0   | 0   | 1        | 0          | 0         | 1             | 1         | 1              | 1                                  |     |
| 0   | 1   | 1        | 0          | 1         | 1             | 0         | 1              | 1                                  |     |
| 1   | 0   | 0        | 0          | 1         | 0             | 0         | 0              | 0                                  |     |
| 1   | 1   | 0        | 1          | 1         | 1             | 1         | 1              | 1                                  |     |

- Formel induziert Funktion $\{0,1\}^{n}\to{0,1}$
- Wenn zwei induzierte Funktionen gleich sind, schreibt man $F\equiv G$
- Notation: 
	- $F\equiv G$ - "F und G sind äquivalent" 
	- $F\equiv \top$ "F ist allgemeingültig" ($\top$ immer-1-Formel) 
	- $F\equiv \bot$ "F unerfüllbar" ($\bot$ immer-0-Formel)

## Beispiel für eine Anwendung: Suche nach neuem Mitbewohner
- 3 Kandidaten (Alf, Berta, Claus)
- 3 Meinungen: 
	- $F = (A\lor B)\land\neg C$
	- $G = B\lor C$
	- $H=\neg B\lor A$

| A   | B   | C   | F   | G   | H   |
| --- | --- | --- | --- | --- | --- |
| 0   | 0   | 0   | 0   | 0   | 1   |
| 0   | 0   | 1   | 0   | 1   | 1   |
| 0   | 1   | 0   | 1   | 1   | 0   |
| 0   | 1   | 1   | 0   | 1   | 0   |
| 1   | 0   | 0   | 1   | 0   | 1   |
| 1   | 0   | 1   | 0   | 1   | 1   |
| 1   | 1   | 0   | 1   | 1   | 1   |
| 1   | 1   | 1   | 0   | 1   | 1   |
## Logische Konsequenz
- F $\vDash$ G, wenn G immer zu 1 auswertet, sofern F zu 1 auswertet. 
- $A\land B \vDash A$
- $F\vDash G \text{ und }G\vDash F \iff F\equiv G$
