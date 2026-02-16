With Stream you can `filter()` and `sort()` data and produce a result `collect()` and `reduce()`.

| method       | description                                                                                                                                                 |
| ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `filter()`   | Filters Elements based on a specified condition. Is used with Lamda `.filter(h -> h.isInfected()` h is the Parameter and h.isInfected() is the Method body. |
| `map()`      | Transforms each Element in a Stream to another value.                                                                                                       |
| `sorted()`   | Sorts Elements.                                                                                                                                             |
| `distinct()` | Removes duplicates.                                                                                                                                         |
| `skip()`     | Skips first n Elements.                                                                                                                                     |
Streams are started with the collection`.stream()` and all the Methods chained onto each other like this:
```Java
long numberOfInfected(Collection<Human> humans) {
	return humans.stream().filter(h -> h.isInfected()).count()
}
```
