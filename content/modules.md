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

Create a new file, app.js and add:
```
var app = angular.module('store', [ ]);
```
Note:
- Create your app.js file, add main app module code
- angular is a call to angular.js
- 'store' will be the name of your application
- [] will be where dependencies go
