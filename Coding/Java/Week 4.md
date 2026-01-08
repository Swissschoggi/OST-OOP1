### Stack
***

* Stapel
* Last in, First out
* Methoden
	* push(e) - Element e auf den Stack legen.
	* pop() - Oberstes Element vom stack nehmen.
	* top() -Referenz auf oberstes Element, ohne zu entfernen.
	* size() - Anzahl Elemente auf dem Stack.
	* isEmpty() - true falls Stack leer ist.
	* isFull() - true falls Stack voll ist.

### ArrayList
***

```Java
stringList.add("OOP1");
stringList.add("ICTh");

stringList.add(0, "Bsys1");             //insert at position 0
String x = stringList.get(1);           //get position 1

stringList.set(0, "Bsys2");             //replace at position 0

stringList.remove("ICTh");
stringList.remove(1);                   //remove at position 1

int size = stringList.size();           //list length
```

Iteration in einer ArrayList:
```Java
for (String s : stringList) {
	System.out.println(s);
}
```

##### Diamond Operator
***

Zeigt den Datentypen an, zum Beispiel `ArrayList<String>` oder `ArrayList<Integer>` 
```Java
ArrayList<String> stringList = new ArrayList<>(); //Compiler erkennt dass nur Arraylist in Frage kommt
```


### Wrapper Klassen
***

Wrapper-Klassen "wrappen" ein Objekt zu einem anderen Primitiven Datentyp.
```Java
Integer.valueOf(123);
Integer wrapper = 123;         //auto-Boxing

int value = wrapper;           //auto-Boxing
wrapper.intValue();
```

### var-Deklarationen
***

```Java
Motorcycle vehicle = new Motorcycle();          //Motorcycle zweimal erwähnt

var vehicle = new Motorcycle();                 //Typ wird berechnet
```

