### Klassen
***

Jede Klasse in eine eigene Datei `Klassenname.java`

``` Java
class Point {
	// Instantvariablen
	int x;
	int y;

}
```
Objekte Instanzieren:
	- new-Operator
Klasse ist Schablone für neues Objekt

```Java
Point a = new Point();

Point b = new Point ();

a == b;
```
* Variable vom Klassentyp Point
* Objekt wird in a und b referenziert
* `new` erzeugt ein neues Objekt von Point

Weil a (oder b) nun die variablen x und y haben kann man diese instanzieren:
```Java
Point a = new Point();
a.x = 0;
a.y = 1;

Point b = new Point();
b.x = 2;
b.y = 3;
```
nun ist x in a 0, y in a 1 und x in b 2, y in b 3.

Wie wir nun sahen spielt die Klasse eine Doppelrolle, zwar als Datentyp `Point a;` und als Schablone `new Point()`

### Methodenaufrufe
***

```Java
class Rectangle {
	int length;
	int width;

	void stretch(int factor) {
		this.length *= factor;
		this.width *= factor;
	}
	
	int getArea() {
		return this.length * this.width;
	}
}
```
Implizites `this` bei Zugriff auf eigene variablen und Aufruf eigener Methoden.
```Java
//Neues Objekt box instanzieren und deren variablen lenght und width setzen.
Rectangle box = new Rectangle();
box.length = 1; box.width = 2;

//durch die Methode stretch, box um 3 strecken.
box.stretch(3);
//neues Objekt Area erstellen dass die Getter methode getArea verwendet.
int area = box.getArea
```

### Gleichheit
***

``` Java
String a = "OOProg";

String b = new String(a);

a == b //false
a.equals(b) //true
```
