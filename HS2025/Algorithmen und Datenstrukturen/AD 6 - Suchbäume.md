#HS2025 #AD 

## Abstrakter Datentyp - Wörterbuch

W: Kollektion von Schlüsseln, keiner mehrfach. 

**Operationen**
- `search(x)`: ist x in W?
- `insert(x)`: füge x in W ein
- `delete(x)`: lösche x aus W

**Idee:** Binärbaum + Suchbaumbedingung

$\forall x$ 
- Alle Schlüssel in $T_{1}$ (Teilbaum links) sind $<x$ 
- Alle Schlüssel in $T_{2}$ (Teilbaum rechts) sind $>x$

Wir haben insert $\le O(h)$ und insert $\le O(h)$ 

**Problem:** Höhe konnte gross werden $\to$ worst case $O(n)$ 

**Idee:** 2-3 Kinder pro Knoten (Struktur flexibler machen)
## 2-3-Bäume

**Externe Variante:**
- Schlüssel nur in Blättern
- innere Knoten: Verwaltungsinformationen: Separatoren $s_{1},s_{2}$ 
- alle Blätter in derselben Tiefe

**Tiefe:** Ein 2-3-Baum des Tiefe $h$ hat $\ge 2^{n}$ Blätter/Schlüssel $\implies h\le O(\log n)$

```
insert(x)
	search(x) -> Blatt B
	füge x als neues Blatt neben B ein
	füge neues Separator bei Eltern ein
```

**Problem:** Elternknoten könnte nun 4 Kinder haben
- Ersetze Elternknoten durch zwei neue Knoten

```
delete(x)
	search(x) -> Blatt B
	lösche B und Separator beim Eltern v
```

**Problem:** v könnte nur noch ein Kind haben 
- Betrachte Nachbar $u$ von $v$
	- Fall 1: $u$ hat 3 Kinder $u \overset{1 \text{ Kind}}\to v$ (adoptieren)
	- Fall 2: $u$ hat 2 Kinder $u+v$ und iterieren

