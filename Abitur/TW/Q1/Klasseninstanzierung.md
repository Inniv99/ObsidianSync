#Q1 #OOP Erstellt am 09.04.2025 um 11:46 Uhr

---
Die *Instanziierung einer Klasse* ist der Vorgang, sobald man ein Objekt aus einer Klasse erstellt. Dabei muss man beachten welche Parameter der Konstruktor vorgibt, falls vorhanden.

Bsp. Normaler Konstruktor
``` cs
class Buch
{
	private string titel;
	private string autor;
	private int vJahr;

	public Buch();
}

...

Main

Buch b1 = new Buch();
```

Bsp. Überladener Konstruktor
``` cs
class Buch
{
	private string titel;
	private string autor;
	private int vJahr;

	public Buch(string titel, string autor, int vJahr)
	{
		this.titel = titel;
		this.autor = autor;
		this.vJahr = vJahr;
	}
}

...

Main

Buch b1 = new Buch("Die Verwandlung", "Franz Kafka", 1915);
```