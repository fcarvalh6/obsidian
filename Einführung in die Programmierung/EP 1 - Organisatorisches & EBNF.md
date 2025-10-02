#EP #HS2025

# Organisatorisches

Handout der Übungen: Dienstag Abend um 18:00
Handin: Dienstag der folgenden Woche um 23:59  

## Prüfung
- Teil 1: Aufgaben zu Grundlagen, 40 Minuten, auf Papier, 1/3 der Note
- Teil 2: Programmieraufgaben, 120 Minuten, Am Computer, 2/3 der Note

## Bonusübungen
- Speziell markierte Übungen ab Woche 5
- Timed Bonus in Woche 9 und 11, 18.11 und 2.12, 17:00-19:00

# EBNF

## Erlaubte Werte

Erlaubte Werte werden mit Formalismus beschreibt (erlaubt automatische Prüfung).
- Menge von erlaubten Zeichenfolgen: **Sprache**
- Eine erlaubte Zeichenfolge in einer Sprache: **Wort**

## EBNF (Extended Backus Naur/Normal Form)

Formalismus zur Beschreibung der Syntax einer Sprache (nur Form/Struktur)

### EBNF-Beschreibung 
- Formale Beschreibung der Struktur einer Sprache
- Besteht aus Menge von EBNF-Regeln
- gibt an, welche Wörter erlaubt sind

### EBNF-Regel
- Form LHS $\leftarrow$ RHS
- linke Seite (LHS): Name der EBNF Regel in eckigen Klammern: \<name>
- Pfeil $\leftarrow$ ausgesprochen als "ist definiert als"
- rechte Seite (RHS)

### Rechte Seite
- Definition (genaue Beschreibung für den Namen LHS)
- kann bestehen aus
	- Zeichen (auch Literal oder Terminal genannt)
	- Namen von EBNF-Regeln (auch Nonterminal genannt)
	- Kombination der vier Kontrollformen ("control forms")

```
<digit_zero> <- 0
<number_zero> <- <digit_zero>
```

### Aufreihung (<\<sequence>>)

**E1 E2 E3** 
- Folge von beliebig viele Elemente
- von links nach rechts gelesen: Reihenfolge ist wichtig
- Jedes Element muss gültige RHS sein

#### Beispiel

Regeln für Beschreibung des Vorlesungssaals 1: "D28"
```
<letter_D> <- D
<digit_2> <- 2
<digit_8> <- 8
<room1> <- <letter_D> <digit_2> <digit_8> (Aufreihung)
```
### Durch EBNF definierte Sprache

- Anwenden einer Regel: ersetzen des Namens durch RHS der Regel
- EBNF hat eine spezielle Regel: **Startregel** ("entry rule")
	- Konvention: letzte Regel ist die Startregel (falls nicht anders erwähnt)
- Sprache der EBNF (informell): Menge aller Zeichenfolgen (ohne Namen), die ausgehend von der Startregel durch wiederholtes Anwenden der EBNF-Regeln erstellt werden können. 

```
<letter_D> <- D
<digit_8> <- 8
<room1> <- <letter_D> 2 <digit_8>
```

Startregel: \<room1>, Sprache: {D28}

### Entscheidung ("decision")

Auswahl ("selection")
```
E1 | E2 | E3
```
- Menge beliebig vieler Alternativen
- Durch senkrechten Strich ("stroke") | getrennt
- Alternative: gültige RHS
- Genau eine der Alternativen wird gewählt

Option ("option")
```
[E1]
```
- Optionales Element
- In eckigen Klammern ("square brackets") 
- Element muss gültige RHS sein
- Kann gewählt werden, muss aber nicht
#### Beispiele

```
<digit> <- 0|1|2|3|4|5|6|7|8|9

<room1> <- D28
<room2> <- E12
<room> <- <room1> | <room2>
```

```
<initials> <- M [H] S

<digit> <- 0|1|2|3|4|5|6|7|8|9
<sign> <- +|-
<number> <- [<sign>]<digit>
```

### Klammern

```
A | B C
```

- Nicht eindeutig 
	- Variante 1: "A oder BC"
	- Variante 2: "AC oder BC"
- Klammern schaffen Klarheit

```
A | (B C) oder (A|B) C 
```

### Wiederholung ("Repetition")

```
{E}
```

- Wiederholung eines Elements
- Element muss gültige RHS sein
- 0,1,2,... Wiederholungen
- In geschweiften Klammern ("curly braces")

#### Beispiele

Ganze Zahlen
```
<digit> <- 0|1|2|3|4|5|6|7|8|9
<sequence> <- <digit>{<digit>}
<sign> <- +|-
<integer> <- [<sign>]<sequence>

<digit> <- 0|1|2|3|4|5|6|7|8|9
<integer> <- [+|-]<digit>{<digit>}
```

Umgangssprachliche Beschreibung
- \<digit> ist definiert als eines der Zeichen 0,...,9
- \<integer> ist definiert als eine Folge von 3 Elementen
	- ein optionales Vorzeichen (eine der Alternativen + und -)
	- ein \<digit>
	- Wiederholung von 0 oder mehr \<digit>s
