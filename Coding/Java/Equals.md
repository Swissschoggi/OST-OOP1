Your own **equals-Method** must always have a **Hashcode** implementation!
for:
```Java
class Point {
	private int x, y;
	public Point(int x, int y) { this.x = x; this.y = y; }
	// Getter und Setter aus Platzgründen weggelassen, sind aber vorhanden.
	@Override
	public boolean equals(Object obj) {
	// Aus Platzgründen weggelassen, die Implementierung ist korrekt.
	}
}
```
Missing is first off, the Hashcode override, the problem that arises would be that a point may have the same coordinates but not the same Hashcode and would therefore be `False`.
```Java
@Test
public void showInconsistency() {
	var point = new Point(1, 2);
	var set = new Hashset<Point>();
	set.add(point);
	if(set.contains(new Point(1, 2))) {
		System.out.println("hashcode implemented --> True")
		}
	else {
		System.out.println("Hashcode not implemented --> False")
		}
	}
```
