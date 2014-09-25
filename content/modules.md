## Let's start our first application

... by creating our first module

Note: These notes work!!!


## wait, what's a module?

Containers for different parts of your application. <!-- .element: class="fragment" -->

Except those containers can use other containers.  <!-- .element: class="fragment" -->

Places where we will write pieces of our application and define dependencies <!-- .element: class="fragment" -->
Note: Mention modular design and a graphic would be helpful here


## wait, what's a module?

- Maintainable and testable <!-- .element: class="fragment" -->
- Readable <!-- .element: class="fragment" -->



## Our first module

Create a new file, app.js, and add:

```
var app = angular.module('store', [ ]);
```

And in our HTML file

```html
<!DOCTYPE HTML>
<html ng-app="store">
    <head>
        <link rel="stylesheet" type="text/css" href="boostrap.min.css"></link>
    </head>
    <body>
        <!--
        <script type="text/javascript" src="angular.min.js"></script>
        <script type="text/javascript" src="app.js"></script>
        -->
    </body>
</html>
```

There, you've made a module.

Note:
- Create your app.js file, add main app module code
- angular is a call to angular.js
- 'store' will be the name of your application
- [ ] will be where dependencies go



## expressions

Angular expressions are JavaScript-like code snippets that are usually placed in bindings such as {{ expression }}. <!-- .element: cite="https://docs.angularjs.org/guide/expression" -->
This allows you to insert values into the HTML

For example:

```
I have {{ 1+2 }} apples ⇨ I have 3 apples
```


## expressions
Some other valid expressions:

```
{{ a+b }}
{{ user.name }}
{{ items[index] }}
```
Note: Show live example
