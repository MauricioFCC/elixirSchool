### **List:**

Las listas son colecciones simples de valores que pueden incluir múltiples tipos; las listas también pueden incluir valores no únicos:

```elixir
[5.5, :Atomo, "Papaya"] # [5.5, :Atomo, "Papaya"]
```

Elixir implementa colecciones de listas como listas enlazadas. Esto significa que acceder a la longitud de la lista es una operación que se ejecutará en tiempo lineal **(O(n))**. Por esta razón, normalmente es más rápido anteponer que agregar:

```elixir
list = [5.5, :Atomo, "Papaya"] # [5.5, :Atomo, "Papaya"]
# Anteponiendo (fast)
[:Pi | list] #[:Pi, 5.5, :Atomo, "Papaya"]
# Anexando (slow)
list ++ ["Papayuela"] # [5.5, :Atomo, "Papaya", "Papayuela"]
```

### **List Concatenation:**

se utiliza `++`

### **list Subtration:**

se proporciona a través del operador `--`

```elixir
[1, 2, "fake"] -- ["fake", 3, 4] # [1, 2, 3, 4]
```

los valores duplicados. Para cada elemento de la derecha, la primera aparición se elimina de la izquierda:

```py
[1,2,2,3,2,3] -- [1,2,3,2] # [2, 3]

```

La resta de listas utiliza una comparación estricta para hacer coincidir los valores.

```elixir
[2] -- [2.0] # [2]
[2.0] -- [2.0] # []
```

### **head and tie:**

La cabeza es el primer elemento de la lista, mientras que la cola es una lista que contiene los elementos restantes. cabeza `hd` y cola `tl`, para trabajar con estas piezas:

```elixir
hd [:Pi, :Atomo, "Papaya"] # :Pi
tl [:Pi, :Atomo, "Papaya"] # [:Atomo, "Papaya"]
```

Se puede utilizar la coincidencia de patrones y el operador contras | para dividir una lista en cabeza y cola.

```elixir
[cabeza | cola] = [:Pi, :Atomo, "Papaya"] # [:Pi, :Atomo, "Papaya"]
cabeza # :Pi
cola # [:Atomo, "Papaya"]
```

### **Tuples:**

Son similares a las listas, pero se almacenan de forma contigua en la memoria. Esto hace que el acceso a su longitud sea rápido pero que la modificación sea costosa; la nueva tupla debe copiarse por completo en la memoria. Las tuplas se definen con llaves:

```elixir
tupla = {:Pi, :Atomo, "Papaya", 2.33} # {:Pi, :Atomo, "Papaya", 2.33}
```

Es común que las *tuplas* se utilicen como mecanismo para devolver información adicional de las funciones; es de utilidad en coincidencia de patrones:

```elixir
{:ok, value} = {:ok, "Successful!"} # {:ok, "Successful!"}
value # "Successful!"
{:ok, value} = {:error} # ** (MatchError) no match of right hand side value: {:error}

```

### **Keyword lists:**

Las listas de palabras clave y los mapas son las colecciones asociativas de Elixir. En Elixir, una lista de palabras clave es una lista especial de tuplas de dos elementos cuyo primer elemento es un átomo; comparten rendimiento con listas:

```elixir

[yo: "programo", hola: "mundo"] # [yo: "programo", hola: "mundo"]
[{:yo, "programo"}, {:hola, "mundo"}] # [yo: "programo", hola: "mundo"]
```

características de las listas de palabras clave resaltan su importancia:

- Las claves son átomos.
- Las llaves están ordenadas.
- Las claves no tienen que ser únicas.

Por estas razones, las listas de palabras clave se usan más comúnmente para pasar opciones a funciones.

### **Maps:**

los mapas son el almacén clave-valor. A diferencia de las listas de palabras clave, permiten claves de cualquier tipo y no están ordenadas. sintaxis `%{}`:

```rb
dev = %{:yo => "Programo", "hola" => :Mundo} # %{:yo => "Programo", "hola" => :Mundo}
dev[:yo] # "Programo"
dev["hola"] # :Mundo
```

A partir de Elixir 1.2, las variables están permitidas como claves de mapa:

```rb

key = "hello" # "hello"
%{key => "world"} # %{"hello" => "world"}
```

Si se agrega un duplicado a un mapa, reemplazará el valor anterior:

```md


dev = %{:yo => "Programo", :yo => "Hola Mundo"} # %{yo: "Hola Mundo"}
```

Hay una sintaxis especial para los mapas que contienen solo átomos como clave:

```elixir
%{yo: "Programo", Hello: "World"} # %{yo: "Programo", Hello: "World"}
%{yo: "Programo", Hello: "World"} == %{:yo => "Programo", :Hello => "World"} # true
```

sintaxis especial para acceder a las claves que son átomos:

```elixir
dev = %{yo: "Programo", Hello: "World"} # %{yo: "Programo", Hello: "World"}
dev.Hello # "World"
```

poseen su propia sintaxis para realizar operaciones de actualización (nota: esto crea un nuevo mapa):

```elixir
dev = %{yo: "Programo", Hello: "World"} # %{yo: "Programo", Hello: "World"}
%{dev | soy: "programador"} # %{soy: "programador", Hello: "World"}
```

Esta sintaxis solo puede usarse para actualizar una clave que ya existe en el mapa de lo contrario saldrá error.

Para crear una nueva clave, en vez utiliza `[Map.put/3](https://hexdocs.pm/elixir/Map.html#put/3)`:

```elixir
dev = %{hello: "world"} # %{hello: "world"}
%{dev | soy: " programador"} # ** (KeyError) key :foo not found in: %{hello: "world"}
map.put(dev, :yo, "programo") # %{:yo, "programo"}
```

```text

```