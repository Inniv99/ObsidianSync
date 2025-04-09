#Q1 #OOP Erstellt am 09.04.2025 um 11:39 Uhr

---

Mit *Setter* können Werte von [[Klassenattribute | Attributen]] außerhalb ihrer eigenen Klasse geändert werden. Sie funktionieren ähnlich wie [[Getter]] nur das sie die Werte verändern. 

Man implementiert sie folgendermaßen:
``` cs
class Bibliothek
{
	private List<Buch> buchliste = List<Buch>();
}
``` 

In dem Bsp. muss die Bibliothek auf den Titel des Buches zugreifen, deshalb braucht man innerhalb der Buch Klasse eine *Methode* SetTitel().

``` cs
class Buch
{
	private string titel;
	private string autor;
	private int vJahr;

	public void setTitel(string titel) { this.titel = titel;}
}
``` 

Innerhalb der Bibliothek benutzt man die *Setter* so;

``` cs
class Bibliothek
{
	public void methode(Buch buch)
	{
		buch.setTitel("Neuer Buchtitel");
	}
}
``` 
