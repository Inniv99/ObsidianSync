#Q1 #OOP Erstellt am 10.04.2025 um 11:24 Uhr

---
Das *Virtual keyword* wird gebraucht um Attribute oder Methoden aus einer Elternklasse, in einer Abgeleiteten klasse veränderbar zu machen.


``` cs
class Tier
{
	private string rasse;
	private string farbe;

	public Tier();

	public virtual void gibLaut(){Console.WriteLine("Grrr");}
}
```