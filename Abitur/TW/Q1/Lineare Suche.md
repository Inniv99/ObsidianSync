Erstellt am 03.05.2025 um 16:12 Uhr

---
Die Lineare Suche sucht von Anfang bis Ende, bis das gesuchte Objekt etc. gefunden wurde. 
```cs
public int lineareSuche(List<int> liste, int wunschZahl)
{
	for(i=0; i<liste.count();i++)
	{
		if(liste[i] == wunschZahl) return i;
	}
	return null;
}
```