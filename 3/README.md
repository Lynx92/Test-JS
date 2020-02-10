# Test 3

En este caso, tenemos un código usando el objeto `Promise` (Promesa). Las *promises* 
(promesas) nos permiten manejar situaciones asíncronas en nuestras ejecuciones, 
pero tenemos un pequeño problema… No es una solución totalmente cross-browser. 
Sabemos que no funciona en Internet Explorer así que nos gustaría saber cómo 
modificarías nuestro código (`test.js`) para que funcione correctamente.


IE No soporta las caracteristicas de ES6, por lo que todo lo que sea arrow functions, let, const, etc 
hay que modificarlo para que sea ES5.

var promise = new Promise(function (resolve, reject) {
    setTimeout(function () {
        if (Math.round(Math.random()) === 1) {
            resolve("Success!");
        } else {
            reject("Fail!");
        }
    }, 1000);
});

promise
    .then(function (successMessage) {
        return console.log("Yes! " + successMessage);
    })
    .catch(function (failMessage) {
        return console.log("No! " + failMessage);
    });
