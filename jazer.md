#Checking Jazer regexp gitbook plugin

```
{% regexp %}
¿Quien descubrió america?
{% solution %}
Cristobal Colon
{% validation %}
/^\s*
     (Cristobal\s+)? # nombre opcional
     Col[oó]n        # apellido
\s*$/ix
{% endregexp %}
```

{% regexp %}
¿Quien descubrió america?
{% solution %}
Cristobal Colon
{% validation %}
/^\s*
     (Cristobal\s+)? # nombre opcional
     Col[oó]n        # apellido
\s*$/ix
{% endregexp %}

```
{% regexp %}
¿Capital de España?
{% solution %}
Madrid
{% validation %}
/\s*[mM]adrid\s*/i
{% endregexp %}
```

{% regexp %}
¿Capital de España?
{% solution %}
Madrid
{% validation %}
/\s*[mM]adrid\s*/i
{% endregexp %}
