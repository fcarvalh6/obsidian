#HS2025 #EP 

- Sonderzeichen in Rahmen
- Ableitungen
- Graphische Darstellung von EBNF-Beschreibungen

## Äquivalenz von EBNF-Beschreibungen

- **Sprache** der EBNF: Menge ihrer legalen Zeichenfolgen
- Zwei EBNF-Beschreibungen $B_{1}$ und $B_{2}$ sind äquivalent falls ihre Sprachen gleich sind:
	- Zeichenfolge legal für $B_{1} \iff$ legal für $B_{2}$ (und vice-versa)

## Syntax versus Semantik

- **Syntax:** Form/Struktur
	- Wird von der EBNF-Formulierung beschrieben
- **Semantik:** Bedeutung/Interpretation
	- falls nicht legal (falsche Syntax), dann keine Bedeutung (undefiniert)

## Kontrollformen II: Rekursion

Name der EBNF-Regel auch auf der rechten Seite
```
<endless_story> <- <paragraph><endless_story>
```

Welche Zeichenfolgen sing gültig?
- Keine! Immer ein Nichtterminal auf der rechten Seite.

Sinnvolle/%

Direkte und Indirekte Rekursion

### Rekursion versus Wiederholung

EBNF-Beschreibung für die Sprache $\{A^{n}B^{n} | n \in \mathbb{N}\}$
```
<equalAB> <- [A<equalAB>B] ... (mit Rekursion)

<?> ... (ohne Rekursion geht es nicht!)
```

- Bei EBNF ist Rekursion mächtiger
