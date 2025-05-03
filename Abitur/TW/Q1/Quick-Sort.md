Erstellt am 03.05.2025 um 16:06 Uhr

---
Der *Quicksort* beruht auf zwei Schritten, welche sich immer wieder wiederholen. Man sucht sich ein *Pivot* heraus und sucht seine richtige Position. Sobald dies geschafft ist werden die Elemente mit dem Pivot verglichen(>Pivot nach rechts, <Pivot nach links) und dementsprechend verschoben. Danach werden wird das Array wie aufgeteilt und man fuhrt den selben Schritt mit den aufgeteilten Arrays aus, per *rekursion*.

Der Quicksort hat den Vorteil, das sein best und average case der selbe ist => $n log(n)$
Worst Case = $n^2$

Pseudocode Quicksort:
```cs
funktion quicksort (links, rechts)

if links < rechts
    t = teilen(links, rechts)
    quicksort(links, t)
    quicksort(t + 1, rechts)
  end
end

funktion teilen(links, rechts)
  
  n = links – 1
  m = rechts + 1

  pivot = Liste[(links + rechts) / 2]
  while Liste[n] < pivot  // wenn Elemente < Pivot-Element ordne sie links ein
    n++
  while Liste [m] > pivot  // wenn Elemente > Pivot-Element ordne sie rechts ein
    m++

  if (n < m)
    int a = Liste[n]
    Liste[n] = Liste[m]
    Liste[m] = a
  else return m
```