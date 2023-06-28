### Integers: 
Soporta; Binarios, Octal y hexadecimal

```sh
0b0110 # 6
0o644 # 420
0x1F # 31
```

### Floats: 
Los números de punto flotante requieren un decimal después de al menos un dígito; tienen doble precisión de 64 bits y admiten `e` para valores de exponente:

```sh
3.14 # 3.14
.14 # ** (SyntaxError) iex:2: syntax error before: '.'
1.0e-10 # 1.0e-10
```

### Booleans: 
Elixir soporta `true` verdadero`false`  y `nil` falso

```sh
true # true
false # false
```

### Atoms: 
Es una constante cuyo nombre es su valor. Son sinónimos de símbolos. `true` y `false` también son átomos.

Los nombres de los módulos en Elixir también son átomos. `MyApp.MyModule` es un átomo válido, incluso si aún no se ha declarado dicho módulo.

Los átomos también se utilizan para hacer referencia a módulos de las bibliotecas de Erlang, incluidos los integrados.

```sh
:foo # :foo
:foo == :bar # false
:true == true # true
:false == false # true
is_atom(MyApp.MyModule) # true
```

módulo de la biblioteca de Erlang

```sh
:crypto.strong_rand_bytes 3 # <<23, 104, 108>>
```

### Strings: 
Se usa codificado en UTF-8 y entre comillas dobles:

```sh
"Hello" # "Hello"
"Soy un string" # "Soy un string"
```

Elixir también incluye tipos de datos más complejos. Aprenderemos más sobre esto cuando aprendamos sobre colecciones y funciones.

Collections -> https://elixirschool.com/en/lessons/basics/collections

Functions -> https://elixirschool.com/en/lessons/basics/functions
