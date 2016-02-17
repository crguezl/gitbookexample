## asciitree

Parece funcionar

Convert indented lines to ascii directory tree for gitbook.

<!--
you can see asciitree in action. 
[https://jianglibo.gitbooks.io](https://jianglibo.gitbooks.io)
-->

[asciitree en GitHub](https://github.com/jianglibo/ascii-tree)


    app
    -main.js
    -helper.js
    -others
    --Brocfile.js
    package.json

```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```


{% asciitree %}
app
-main.js
-helper.js
-others
--Brocfile.js
package.json
{% endasciitree %}


