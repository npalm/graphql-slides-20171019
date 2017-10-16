## REST API

<div class="fragment">
Resource: `/talks`
</div>
<pre class="fragment"><code>
[
  {
    "title" : "GraphQL - The Next API Language",
    "speaker" : {
      "username" : "niek",
      "href" : "http://geecon.cz/speakers/niek"
    }
  }
  {
    "title" : "Built To Last ...and the end of migrations",
    "speaker" : {
      "username" : "adam",
      "href" : "http://geecon.cz/speakers/adam"
    }
  }
]

</pre></code>


!SUB
## REST API
Resource `/speakers/niek`

```
{
  "username" : "niek",
  "name" : "Niek Palm",
  "twitter" : "niekos77",
  "blog" : "https://040code.github.io",
  "github": "npalm",
  "city" : "Eindhoven",
  "shoppinglist" : {
    "href" : "http://geecon.cz/speakers/niek/shoppinglist"
  }
}
```

!SUB
## REST Architecture
![rest](images/rest-architecture.png)

!SUB
## REST Architecture
![rest-2](images/rest-architecture-2.png)
