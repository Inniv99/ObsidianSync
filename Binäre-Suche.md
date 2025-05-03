Erstellt am 03.05.2025 um 16:17 Uhr

---
Die Binäre-Suche wird vor allem bei großen Listen oder Arrays verwendet. Sie benötigt jedoch diese Sortiert um zu funktionieren. 

Das Prinzip dieses Suchverfahrens ist, dass der mittlere Index als erster Referenzwert genommen wird und mit der gesuchten Zahl verglichen wird. 

Referenzwert < Zahl =>rechte Hälfte wird weiter durchsucht mit dem selben verfahren 
Referenzwert > Zahl => linke Hälfte wird weiter durchsucht

Jedes mal, wenn die Liste halbiert wird, ein neuer Referenzwert genommen(der mittlere Index).

```cs

static int BinaereSuche(List<int> liste, int wunschZahl)
{
    int links = 0;
    int rechts = liste.Count - 1;

    while (links <= rechts)
    {
        int mitte = (links + rechts) / 2;

        if (liste[mitte] == wunschZahl)
            return mitte;

        if (liste[mitte] < wunschZahl)
            links = mitte + 1;
        else
            rechts = mitte - 1;
    }

    return -1; // Zahl nicht gefunden
}
```