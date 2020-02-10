# Test 2

El fragmento de código de nuestro fichero `test.js` nos devuelve un output no 
deseado. Queremos imprimir un valor incremental a cada segundo pero lo que 
nos devuelve el código es el mismo valor en cada iteración. 

1. Sin necesidad de ejecutar el código, ¿sabrías decirnos qué valor imprimiría
 por consola el script? ¿Cuál es el motivo?

    Daría 5 5 5 5 5, ya que el hecho de usar var para definir 'i' hace que se trabaje con solo un
    scope y eso provoca que hasta que no resuelve no saca el resultado.

2. Sabiendo que el output que buscamos es el que encuentras bajo estas líneas… 
¿Cómo solucionarías el fragmento de código para que el output sea el deseado?

Usamos let en vez de var para definir 'i' para así crear un nuevo scope cada vez que hace una iteración

for (let i = 0; i < 5; i++) {
    setTimeout(function() {
        console.log(i);
    }, 1000)
}


```
    > 0
    > 1
    > 2
    > 3
    > 4
```