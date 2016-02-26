## Variables inside Templates

En book.json:

```
{

    "variables": {
        "myVariable": "Hello World"
    },
    "plugins": ["katex", "quiz", "quizzes" , "asciitree",
                "ace", "exercises-tmp-fixed-6", "youtube",
 ....
```

```
`temperature = ` {{ book.myVariable }}
```

will be:

`temperature = ` {{ book.myVariable }}


