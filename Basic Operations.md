## Operaciones basicas

#### Arithmetics:

Elixir admite los operadores básicos `+, -, * y /` como cabría esperar. Es importante recordar que `/` siempre devolverá un flotante:

```sh { name= mimeType=text/plain }
2 + 2 # 4
2 - 1 # 1
2 * 5 # 10
10 / 5 # 2.0
```

Si necesita la división de enteros o el resto de la división (es decir, módulo), Elixir viene con dos funciones útiles para lograrlo:

```sh
div(10, 5) # 2
rem(10, 3) # 1
```

### Booleans:

Elixir proporciona `or || and && y not !` operadores booleanos. Estos admiten cualquier tipo. En elixir and y or en realidad se asigna a andalso y orelse en Erlang.

### Comparison:

Elixir viene con todos los operadores de comparación a los que estamos acostumbrados:

```sh
1 == 1 # Comparacion
1 != 2 # Diferencia
1 === "1" # Comparacion estricta (Simbolo y tipo)
1 !== "1" # Diferencia estricta
2 <= 3 # meno o igual
2 >= 3 # menor o igual
1 > 2 # Mayor que
2 < 3 # Menor que
```

Orden de clasificación de las comparaciones:
número < átomo < referencia < función < puerto < pid < tupla < mapa < lista < cadena de bits

### String Interpolation:

Similar a ruby

```sh
name = "jhon Doe" # "jhon Doe"
"Hello #{name}" # "Hello jhon Doe"
```

### String Concatenation: 
se usa ```<>``` para concatenar dos cadenas

```sh
name = "jhon Doe" # "jhon Doe"
"Hello " <> name # "Hello jhon Doe"
```
