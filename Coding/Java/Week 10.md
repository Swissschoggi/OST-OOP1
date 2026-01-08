### Exceptions
- throws-Klausel in Methodenkopf
	• `throws ExceptionType1, ExceptionType2`

```Java
void test() {
	try {
		String s = null;
		String c = clip(s);
		System.out.println(c);
	} catch (Exception e) {
		System.out.println("Error occurred. Test failed.");
	}
}
```
![[Pasted image 20260102171424.png]]
