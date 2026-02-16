Constructors are the Data "Gerüst" of your code.
```Java
Public class chapter {
	private ArrayList<byte> bytes;
	private int index;
}

Public class Podcast {
	private Arraylist<chapter> chapters;
	
	Public Podcast {}
	
	Public Podcast (ArrayList chapters) {
		this.chapters = chapters;
	}
}
```
`this.chapters` refers to `	private Arraylist<chapter> chapters;` and `chapters` refers to the Parameter passed on in the Parameterlist `ArrayList chapters`.
