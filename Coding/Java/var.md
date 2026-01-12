`var` replaces the Type field, it can be used if the type is already indicated:
```Java
class Demo1 {
    public static void main(String[] args) {

        var x = 100;        // int
        var y = 1.9;        // double
        var z = 'a';        // char
        var p = "tanu";     // String
        var q = false;      // boolean
    }
}
```
`var` cannot be used outside of Methods, or constructors.
It can also not be used as a Generic Type:
```Java
var<var> list = new ArrayList<Integer>;     // Invalid
```

`var` also only works when it is initialized, else there will be an error:
```Java
var x = 5; // Works
vat y;     // Error
```

It's usually easier to use the Type but for complex Types such as `HashMap` or `ArrayList` you can use var:
```Java
// Without var
ArrayList<String> cars = new ArrayList<String>();

// With var
var cars = new ArrayList<String>();
```
