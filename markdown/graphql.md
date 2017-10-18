## What is GraphQL not

<ul>
  <li class="fragment">Not a database</li>
  <li class="fragment">A standard (not yet)</li>
  <li class="fragment">A library</li>
  <li class="fragment">Language specific</li>
</ul>

!SUB
## What is GraphQL
<ul>
  <li class="fragment">A query language allow to fetch what you what</li>
  <li class="fragment">Flexible</li>
  <li class="fragment">A specification</li>
</ul>
<div class="fragment">
![spec](images/spec.png)
</div>

!SUB
## Who is using GraphQL


<img data-src="images/users.png" height="60%" width="60%">

http://graphql.org/users/


!SUB
## What is GraphQL
<table class="reveal">
  <tr>
    <td class="fragment"><img data-src="images/graphql-describe.png"></td>
    <td class="fragment"><img data-src="images/graphql-ask.png"></td>
    <td class="fragment"><img data-src="images/graphql-get.png"></td>
  </tr>
</table>


!SUB
## Hello World

![hello-1](images/hello1.png)

!SUB
## Hello World
![hello-2](images/hello2.png)


!SUB
# Model
<img data-src="images/datamodel-white.png" height="80%" width="80%">


!SUB
# DEMO
<img data-src="images/giphy-hackerman.gif" height="80%" width="80%">


!SUB
### Demo internals
![demo-1-1](images/demo-1-1.png)

!SUB
### Demo internals
![demo-1-3](images/demo-1-2.png)

!SUB
### Demo internals
![demo-1-3](images/demo-1-3.png)

!SUB
### Demo internals

<div class="fragment" align="left">
<small>HTTP Request (POST)</small>
<pre><code>
{
	"query": "query { allTalks { title } }"
}
</pre></code>
</div>

<div class="fragment" align="left">
<small>HTTP Response</small>
<pre ><code>
{
  "data": { ... }
}
</pre></code>

<div align="center">
[https://github.com/npalm/graphiql](https://github.com/npalm/graphiql)
</div>
</div>

!SUB
### GraphQL Queries : Arguments

In REST you pas a single set of argument as query parameters in GraphQL **every field and nested object** can get its own set.

<pre class="fragment"><code>
{                       {
  Person(id: 1)           "data": {
    name                     "Person" {
  }                             "name": "Niek Palm"
}                            }
                          }
                        }
</code></pre>


!SUB
### GraphQL Queries : Aliases
**Aliases** let you rename the result of a field to anything you want.
<pre class="fragment"><code>
{                                 {
  Speaker: Person(id: 1)            "data": {
    fullName: name                    "Speaker" {
  }                                       "fullName": "Niek Palm"
}                                      }
                                    }
                                  }

</code></pre>

!SUB
### GraphQL Queries : Fragments
GraphQL includes reusable units called **fragments**. Fragments let you construct sets of fields, and then include them in queries.

<pre class="fragment"><code>
fragment details on Person {
  name
  github
}
</code></pre>


!SUB
### GraphQL Queries : Variables
A GraphQL query can be parameterized with variables, maximizing query reuse, and avoiding costly string building in clients at runtime.


!SUB
# DEMO
<img data-src="images/giphy-programming.gif" height="60%" width="60%">


!SUB
### GraphQL Mutations

Any operations that cause writes should be sent explicitly via a mutation. To call a mutation, you must use the keyword **mutation** before your GraphQL query


!SUB
### GraphQL Mutations

```
mutation {
 createPerson(name: "Edsgar") {
   id
   name
 }
}
```

!SUB
# DEMO
<img data-src="images/giphy-bart.gif" height="60%" width="60%">


!SUB
### GraphQL Subscriptions
Subscribing to events


<pre class="fragment"><code>
subscription TalkMessage {
  talkMassage(talkId: 1) {
    message
  }
}
</pre></code>
<pre class="fragment"><code>
"data" : {
  "talkMassage" : {
    "message" : "moved to room ..."
  }
}
</pre></code>


!SUB
## Schema
A GraphQL schema is in essence the definition of a type system

<pre><code class="fragment">
schema {
  query: Query
  mutation: Mutation
}
</code><code class="fragment">
type Query {
    person(name: String!): Person
}
</code><code class="fragment">
type Person {
  id: ID!
  name: String
}

</code></pre>


!SUB
### How can start implementing
![lang](images/graphql-languages-lib.png)

[GraphQL.org](https://graphql.org) and [Awesome GraphQL](https://github.com/chentsulin/awesome-graphql)

!SUB
![](images/sample-java.png)
<div class="fragment">
<img data-src="images/sample-java-graphiql.png" height="70%" width="70%">
[https://github.com/npalm/graphql-java-demo](https://github.com/npalm/graphql-java-demo)
</div>

!SUB
### Java example
- Spring Boot and GraphQL Spring Boot Starter <!-- .element: class="fragment" -->
- GraphQL (schema first) via GraphQL tools <!-- .element: class="fragment" -->
- GraphQL interface provided <!-- .element: class="fragment" -->
- Build via Gradle (and Docker) <!-- .element: class="fragment" -->

!SUB
![](images/sample-javascript.png)
<div class="fragment">
<img data-src="images/sample-javascript-graphiql.png" height="70%" width="70%">
[https://github.com/npalm/graphql-js-demo](https://github.com/npalm/graphql-js-demo)
</div>
