## expressions and binding

Angular expressions are JavaScript-like code snippets that are usually placed in **bindings** such as `{{ expression }}`. <!-- .element: cite="https://docs.angularjs.org/guide/expression" -->
This allows you to insert values into the HTML

For example:

```
I have {{ 1+2 }} apples ⇨ I have 3 apples
```


## expressions and binding
Some other valid expressions:

```
{{ a+b }}
{{ user.name }}
{{ items[index] }}
```
Note:
- Show live example
- no loops, conditionals, if/else
- Where do those variables come from? (lead into controllers)
- You don't really want to do logic in your view!
- Binding is best for displaying data and showing off



## expressions and binding
Let's add an input into our view and add an ng-model attribute:
```
<input type="text" ng-model="user.name" />
```

Then add a binding somewhere on the page
```
<h1>Hi, {{user.name}}</h1>
```


## expressions and binding
Binding can be used for more than just printing text
```
<input type="text" ng-model="user.status" />
```

```
<h2 class="text-{{user.status}}">Your current status: {{user.status}}</h2>
```
Note:
Live example
show manipulating classes with user.status
take a momement to make sure everyone has gotten this far
break if it's been a while
