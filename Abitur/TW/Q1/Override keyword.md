Erstellt am 10.04.2025 um 11:29 Uhr

---
Das *Override Keyword* ermöglicht es abgeleitete Methoden gleichnamig zu lassen, dabei aber die Eigenschaften und Funktion der Methode zu verändern.

``` cs
class Hund:Tier
{
	private double größe;
	...

	public override void gibLaut(){Console.WriteLine("Wuff!"); }
}
```

Somit hätte man für die Hunde Klasse ``gibLaut()`` das Geräusch Grrr zu Wuff geändert ohne diese Änderung an alle abgeleiteten Klassen vorzunehmen.