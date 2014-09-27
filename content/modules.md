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
var app = angular.module('collection', [ ]);
```

And in our HTML file

```html
<!DOCTYPE HTML>
<html ng-app="collection">
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

You've made a module!

Note:
- Create your app.js file, add main app module code
- angular is a call to angular.js
- 'collection' will be the name of your application, make sure to add it!
- [ ] will be where dependencies go
- Side note about ng-app
    - It's telling angular that everything inside of html belongs to the app 'collection'
    - It could even be empty
