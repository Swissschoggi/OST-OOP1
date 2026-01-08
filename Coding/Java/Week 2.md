### Methods
***
###### Methoden Aufruf:
```Java 
starLine();
```
Ruft Methode auf.
###### Deklaration:
```Java
static void starLine() {
	or (int i = 1; i <= 16; i++) {
		System.out.print('*');
	}
	System.out.println();	
}
```
Deklariert was in der Methode passiert.

### Method-Stack
***
Ein Method-Stack ist die Reihenfolge von Methodenaufrufen die auf den Stack gestellt werden.
Zum Beispiel mit diesem Code:
```Java
public static void main(String[] args) {
	starSquare();
	}
		static void starSquare() {
			for (int i = 1; i <= 16; i++) {
				starLine()
			}
		}
					Static void starLine() {
						for (int i = 1; i <= 16; i++) {
							System.out.print('*');
							}
							System.out.println();
					}
```


|        |
| ------ |
|        |
|        |
| main() |

|              |
| ------------ |
|              |
| starSquare() |
| main()       |

|              |
| ------------ |
| StarLine()   |
| starSquare() |
| main()       |

| System.out.print() |
| ------------------ |
| StarLine()         |
| starSquare()       |
| main()             |

### Static
***
##### Method
Statische Methoden müssen nicht mit einem Objekt Initialisiert werden:
``` Java
public class MathUtils {
    // Static method - no object needed
    public static int add(int a, int b) {
        return a + b;
    }
    
    // Instance method - needs object
    public int multiply(int a, int b) {
        return a * b;
    }
}

// Usage:
int sum = MathUtils.add(5, 3);  // No object needed

MathUtils util = new MathUtils();
int product = util.multiply(5, 3);  // Object required
```
##### Variable
Ist durch die ganze klasse anwendbar:
``` Java
public class Car {
    // Static variable - shared by all Car objects
    public static int totalCarsCreated = 0;
    
    // Instance variable - unique to each Car object
    public String model;
    
    public Car(String model) {
        this.model = model;
        totalCarsCreated++;  // Increment the shared counter
    }
}

// Usage:
Car car1 = new Car("Toyota");
Car car2 = new Car("Honda");
System.out.println(Car.totalCarsCreated);  // Output: 2 (shared count)
```

### Parameter
***
Gibt an was bei der initialisierung für Daten an die Methode gegeben werden:
```Java
static void symbolLine(char symbol, int amount) {
	for (int i = 1; i <= amount; i++) {
		System.out.print(symbol);
	}
	System.out.println();	
}

//Argumente werden jetzt hier weitergegeben.
symbolLine("*", 20);
```

### Typkonversion
***
* Informationsverlust möglich
* Cast-Operator zwingend

```Java
short a; int b; long c;

b = (int)c;
a = (short)b;
a = (short)c;
```
