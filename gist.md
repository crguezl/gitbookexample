See [gitbook-plugin-gist](https://www.npmjs.com/package/gitbook-plugin-gist).

Configure the plugin in your `book.json`:

```javascript
{
    "plugins": ["gist"]
}
```

Include a Gist using the gist block:


         
        {% gist id="SamyPesse/6ceb8cb8d531ffab75f0" %}{% endgist %}
         
        {% gist id="SamyPesse/6ceb8cb8d531ffab75f0",file="README.md" %}{% endgist %}
         
        {% gist id="SamyPesse/6ceb8cb8d531ffab75f0",hideFooter=true %}{% endgist %}}



{% raw %}
{% gist id="SamyPesse/6ceb8cb8d531ffab75f0",file="README.md" %}{% endgist %}
{% endraw %} 

