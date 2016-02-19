##exercises


          {% exercise %}
          Define a variable `x` equal to 10.
          {% initial %}
          var x =
          {% solution %}
          var x = 10;
          {% validation %}
          assert(x == 10);
          {% context %}
          // This is context code available everywhere
          // The user will be able to call magicFunc in his code
          function magicFunc() {
              return 3;
          }
          {% endexercise %}

Parece funcionar aunque me da un par de errores en la consola:

        GET http://localhost:4000/'+options.staticBase+'/plugins/gitbook-plugin-exercises/jsrepl/jsrepl.js?_=1455723481008 404 (Not Found)send @ app.js:8631jQuery.extend.ajax @ app.js:8167jQuery._evalUrl @ app.js:8324jQuery.fn.extend.domManip @ app.js:5433jQuery.fn.extend.replaceWith @ app.js:5343(anonymous function) @ app.js:24564fire @ app.js:3100self.fireWith @ app.js:3212done @ app.js:8265(anonymous function) @ app.js:8606

        VM93:1 Uncaught SyntaxError: Unexpected identifierjQuery.extend.globalEval @ app.js:329jQuery.ajaxSetup.converters.text script @ app.js:8662ajaxConvert @ app.js:7797done @ app.js:8216(anonymous function) @ app.js:8606send @ app.js:8631jQuery.extend.ajax @ app.js:8167jQuery._evalUrl @ app.js:8324jQuery.fn.extend.domManip @ app.js:5433jQuery.fn.extend.replaceWith @ app.js:5343(anonymous function) @ app.js:24564fire @ app.js:3100self.fireWith @ app.js:3212done @ app.js:8265(anonymous function) @ app.js:8606


{% exercise %}
Define a variable `x` equal to 10.
{% initial %}
var x =
{% solution %}
var x = 10;
{% validation %}
assert(x == 10);
{% context %}
// This is context code available everywhere
// The user will be able to call magicFunc in his code
function magicFunc() {
    return 3;
}
{% endexercise %}

Jazer ha encontrado el problema:

plugin,


            carpetadelproyecto/node_modules/gitbook-plugin-exercises

y editar el archivo

            index.js.

Se cambia la linea

          "body:end": function(options) {
                          return '<script src="'+options.staticBase+'/plugins/gitbook-plugin-exercises/jsrepl/jsrepl.js" id="jsrepl-script"></script>';
                      }

por

        "body:start": function(options) {
                        return '<script src="'+options.staticBase+'/plugins/gitbook-plugin-exercises/jsrepl/jsrepl.js" id="jsrepl-script"></script>';
                    }

(la diferencia está en `body:end` por `body:start`)
guardamos y ya deberia de funcionar correctamente el plugin.

Otra solución: usar el plugin  [ exercises-tmp-fixed-6](https://plugins.gitbook.com/plugin/exercises-tmp-fixed-6)
que es un fork temporal de `exercises` (Esto fué escrito el 19/02/2016).

Otro ejemplo de uso:

{% exercise %}
¿Quién descubrió América?
{% initial %}
var x =
{% solution %}
var x = "Cristóbal Colón";
{% validation %}
x.match(/crist[oó]bal\s+colón/i)
{% context %}
// This is context code available everywhere
// The user will be able to call magicFunc in his code
function magicFunc() {
    return 3;
}
{% endexercise %}
