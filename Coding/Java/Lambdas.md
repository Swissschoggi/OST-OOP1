Lambdas are an easy way to write Methods
```Java
(parameters) -> expression
(parameters) -> { statements; }
```
if i have the following lamda:
```Java
(Person p) -> {
    String value = p.getName();
    value += p.getAge();
    return value;
}
```
I can make it easier with the following steps:
	It gets the Name and assigns it to a string `String value = p.getName();`
	to that it adds the age of the person with `value += p.getAge();`
	and finally returns the String with `"Name Age"`
you can make this easier by combining the steps:
```Java
p -> p.getName() + p.getAge()
```
You can leave the type person away as Java knows this from context.
`getName()` and `getAge()` gets automatically converted to a string.

##### Functional Interface
The functional interface has only one abstract method such as the Lamda above.
```Java
@FunctionalInterface //optional
interface Function { //name can be set as you want
	String apply(Person p); //it takes a Person p and gives out a String
}
```
`apply` is just a placeholder name for how you choose to name the Method using the Lambda