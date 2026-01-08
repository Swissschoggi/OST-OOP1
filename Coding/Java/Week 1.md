### Primitive Datentypen
***

| Typ     |                        |                    |
| ------- | ---------------------- | ------------------ |
| boolean | Boolscher Wert         | true, false        |
| char    | Textzeichen            | "a", "b", "0", "ë" |
| byte    | Ganzzahl (8bit)        | -128 bis 127       |
| short   | Ganzzahl (16bit)       | -32'768 bis 32'767 |
| int     | Ganzzahl (32bit)       | -2³¹ bis 2³¹-1     |
| long    | Ganzzahl (64bit)       | -2⁶³ bis 2⁶³-1     |
| float   | Gleitkommazahl (32bit) | 2 * 10⁴            |
| double  | Gleitkommazahl (64bit) |                    |
### Array
***

```Java
//a)
int length = 5;
int [] a = new int[length];

//b)
a[2] = 1;
```

a)

| a[0] | a[1] | a[2] | a[3] | a[4] |
| ---- | ---- | ---- | ---- | ---- |
| 0    | 0    | 0    | 0    | 0    |

b)

| a[0] | a[1] | a[2] | a[3] | a[4] |
| ---- | ---- | ---- | ---- | ---- |
| 0    | 0    | 1    | 0    | 0    |

### Mehrdimensionales Array
***

```Java
int[][] m = new int[2][3];

m = [1] [2] = 3;
```

Erster Index Links
Zweiter Index unten

| index 0 |    0    |    0    |    0    |
| :-----: | :-----: | :-----: | :-----: |
| index 1 |    0    |    0    |    3    |
|         | index 0 | index 1 | index 2 |
