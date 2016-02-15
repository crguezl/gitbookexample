# Introduction a Algunos Plugins de gitbook

## Latex
Ejemplo de Látex:

`Inline math: $$\int_{-\infty}^\infty g(x) dx$$`:

Inline math: $$\int_{-\infty}^\infty g(x) dx$$

Otro ejemplo:

$$a \times x^2 + b \times x + c = 0$$



# Quiz

[Ejemplo de uso del plugin quiz](https://github.com/chudaol/gitbook-plugin-quiz):

<quiz name="Gitbook Quiz">
    <question multiple>
        <p>What is gitbook used for?</p>
        <answer correct>To read books</answer>
        <answer>To book hotel named git</answer>
        <answer correct>To write and publish beautiful books</answer>
        <explanation>GitBook.com lets you write, publish and manage your books online as a service.</explanation>
    </question>
    <question>
        <p>Is it quiz?</p>
        <answer correct>Yes</answer>
        <answer>No</answer>
    </question>
</quiz>

## Quizzes

¡No funciona!

---

Here's a quiz about Gitbook

|                  | Good | Bad |
| ---------------- | ---- | --- |
| What is Gitbook? | (x)  | ( ) |

> Gitbook is good

What does Gitbook support?
- [x] Table-based questions with radio buttons
- [x] Table-based questions with checkboxes
- [ ] Telepathy
- [x] List-based questions with checkboxes
- [x] List-based questions with radio buttons
- [ ] Moon-on-a-stick

> Gitbook supports table and list based quiz questions using either radio buttons or checkboxes.
>
> Gitbook is not telepathic and does not give you the moon on a stick.

---

## asciitree

No parece funcionar

Convert indented lines to ascii directory tree for gitbook.

you can see asciitree in action. 
[https://jianglibo.gitbooks.io](https://jianglibo.gitbooks.io)

    app
    -main.js
    -helper.js
    -others
    --Brocfile.js
    package.json

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

## ace

The [plugin](https://plugins.gitbook.com/plugin/ace) has a basic syntax:

{%ace edit=true%}
// This is a hello world program for C.
#include <stdio.h>

int main(){
  printf("Hello World!");
  return 1;
}
{%endace%}

* `lang`: the language for syntax highlight. 
For the full list of keyword for each language, please check out the github page of ace [here](https://github.com/ajaxorg/ace-builds/tree/master/src-min-noconflict), 
all the related files are starting with prefix `mode-`. For instance:

        mode_c_cpp.js ----> c_cpp
        mode_java.js ----> java
        ...

