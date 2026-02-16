
```Java
class X {}
class Y extends X {}
class Z extends Y {}

public class Main {
	Public static void print(Y y) {
		System.out.println("z");
	}
	
	Public static void print(Z z) {
		System.out.println("z");
	}
	
	Public static void main(String[] args) {
		print((Y) new Y());       // Ausgabe 1
		print((Z) new Z());       // Ausgabe 2
		print((Y) new Z());       // Ausgabe 3
		print((Z) new Y());       // Ausgabe 4
	}
}
```
**Wie lauten die vier Ausgaben?**
*Overloading*

| Ausgabe       | Ausgabe auf der Konsole                                                                                                                                             |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Ausgabe 1** | y                                                                                                                                                                   |
| **Ausgabe 2** | z                                                                                                                                                                   |
| **Ausgabe 3** | `new Z()` creates an object of type `Z`<br>`(Y) new Z()` is an **upcast**, `Z` is a sublcass of `Y`, runtime type is `Z`, but **compile-time type** is `Y`<br>--> y |
| **Ausgabe 4** | `Error` due to it being compile time type of `Y` but `Y` is a superclass to `Z` and not a component of `Z`                                                          |
#### Overloading / Overloading
[[Week 6#Overriding]] 
[[Week 6#Overloading]]

#### Another exercise
```Java
class Graphic {
	void moveTo(Graphic other) {
		System.out.println("Method 1");
	}
}

class Circle extends Graphic {
	void moveTo(Graphic other) {
		System.out.println("Method 2");
	}
	void moveTo(Circle other) {
		System.out.println("Method 3")
	}
}

Circle c = new Circle(); //Dynamic Type: Circle
Graphic g = new Circle(); //Dynamic Type: Circle
```
*Overriding (runtime --> **dynamic types**)* + *Overloading (compile-time --> **static types**)*

| Aufruf                     | Methode                                                                                                                                                                                                |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **c.moveTo(g)**            | because the two main methods are overriding, `c` is dynamic type `Circle` and chooses the Circle class.<br>The two Methods in `Circle` are overloading so the static type of g is Graphic --> Method 2 |
| **c.moveTo(c)**            | Method 3                                                                                                                                                                                               |
| **g.moveTo(c)**            | Method 2                                                                                                                                                                                               |
| **g.moveTo(g)**            | Method 2                                                                                                                                                                                               |
| **((Graphic)c).moveTo(g)** | Casting only changes the static type, not the dynamic type, so again it is a `Circle` with static type `Graphic` --> Method 2                                                                          |
| **((Circle)g).moveTo(c)**  | Method 3                                                                                                                                                                                               |
#### Type casting primitive datatypes
```Java
int i = 1;
long l = 2;
float f = .1f;
double d = 0.2;
```

| Ausdruck | Result             | Type    | Explanation                                |
| -------- | ------------------ | ------- | ------------------------------------------ |
| i / 2    | 0                  | int     | rounds to 0 and both are ints              |
| i / 2.0  | 0.5                | double  | converts to double as 2.0 is a double      |
| f + d    | .3                 | double  | the float will become a double             |
| i == 1   | false (apparently) | boolean | no clue why this is false in the solutions |
| f / 0    | infinity           | float   |                                            |
