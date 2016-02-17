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

No parece funcionar

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

