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


