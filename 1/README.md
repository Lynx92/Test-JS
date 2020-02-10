# Test 1

Para responder a este test encontrarás un archivo llamado `test.js` en esta
misma carpeta donde hay un pequeño fragmento de código que deberás analizar
y responder a las siguientes cuestiones.

1. En el fragmento de código de nuestro archivo (`test.js`) podemos encontrar
   hasta 3 variables. ¿Podrías decirnos cuál sería el valor de todas ellas al
   finalizar la ejecución del script?

var rgb = {
red: "#FF0000",
green: "#00FF00",
blue: "#0000FF",
white: "#FFFFFF",
black: "#000000"
};

var wb = {
white: "#FFFFFF",
black: "#000000"
};

var colors = {
red: "#FF0000",
green: "#00FF00",
blue: "#0000FF",
white: "#FFFFFF",
black: "#000000"
};

La función Object.assign() muta el origen también

2. Modifica el código para que las variables `rgb` y `wb` mantengan sus valores
   iniciales y `colors` tenga los valores de ambas al finalizar la ejecución del
   script.

     var rgb = {
        red: "#FF0000",
        green: "#00FF00",
        blue: "#0000FF"
   };

    var wb = {
        white: "#FFFFFF",
        black: "#000000"
    };

    var colors = { ...rgb, ...wb };

    console.log(rgb);
    console.log(colors);

3. Además, tenemos un bug localizado en dispositivos con Internet Explorer…
   El código de nuestro script no funciona y necesitamos que se ejecute también
   en este navegador. ¿Sabrías identificar cuál es el problema? ¿Qué solución nos
   propones?

   El problema es que IE no soporta la función Object.assign(), por lo tanto habría que hacerlo manualmente en una función como por ejemplo:

   function assignIE(target) {
    for (var i = 1; i < arguments.length; i++) {
        var source = arguments[i];
        for (var key in source) {
            if (source.hasOwnProperty(key)) {
            target[key] = source[key];
            }
        }
    }
    return target;
   }

    let result = assignIE(colors);
    console.log(result);



**PS**: No es estrictamente necesario tener Internet Explorer para poder identificar y/o resolver el bug.
