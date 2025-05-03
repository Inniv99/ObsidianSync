Erstellt am 03.05.2025 um 16:07 Uhr

---
Der *Bubble Sort* ist eine eher selten genutzter Sotieralgorithmus aufgrund seiner hohen Zeitkomplexitat => $n^2$

Die Funktionsweise ist die, dass das erste element mit dem zweiten verglichen wird und falls das erste größer ist tauscht man (i>i+1?). Das Ganze wird wiederholt, bis das Array oder die Liste sortiert ist.

```cs
  laenge = x.Anzahl;
  for b = 1 to laenge
    for k = 0 to (laenge-b)
      if zahl[k] >  zahl[k+1]
        c = zahl [k]
        zahl[k] = zahl[k+1]
        zahl[k+1] = c
```