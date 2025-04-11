#Q1 #OOP Erstellt am 09.04.2025 um 11:20 Uhr

---

Sollte ein Objekt in [[Aggregation]] zu einer anderen Klasse stehen, benötigt man *Getter*, damit dieses Objekt auf die Werte einzelner [[Klassenattribute]] zugreifen kann.

Man implementiert sie folgendermaßen:
``` cs
class Bibliothek
{
	private List<Buch> buchliste = List<Buch>();
}
``` 

In dem Bsp. muss die Bibliothek auf den Titel des Buches zugreifen, deshalb braucht man innerhalb der Buch Klasse eine *Methode* GetTitel().

``` cs
class Buch
{
	private string titel;
	private string autor;
	private int vJahr;

	public string getTitel() {return titel;}
}
``` 

Innerhalb der Bibliothek benutzt man die *Getter* so;

``` cs
class Bibliothek
{
	public void methode(Buch buch)
	{
		buch.getTitel();
	}
}
``` 
