## Controllers
Controllers are where we define our app’s behavior by defining functions and values. <!-- .element: class="fragment" -->

But for now we're just going to throw some data in there. <!-- .element: class="fragment" -->

```
var user = {
    name: 'Dan Lucas',
    status: 'primary'
};
```
<!-- .element: class="fragment" -->



## Controllers
First we need to add a controller to our app
```
(function(){
    var app = angular.module('store', [ ]);

    app.controller('UserController', function(){

    });
})();
```



## Controllers
Then assign the data to a property
```
(function(){
    var app = angular.module('store', [ ]);

    app.controller('UserController', function(){
        this.user = user;
    });

    var user = {
        name: 'Dan Lucas',
        status: 'primary'
    };
})();
```



## Attaching the Controller
```
<div class="container" ng-controller="UserController as user">
    <h1>Hi, {{user.user.name}}.</h1>
    <h2 class="text-{{user.user.status}}">Your current status: {{user.user.status}}</h2>

    <!-- <input type="text" ng-model="store.user.name" /> -->
    <!-- <input type="text" ng-model="store.user.status" /> -->
</div>
```



## Understanding Scope
The "scope" of the controller only works inside of the container

```
<div class="container" ng-controller="UserController as user">
    <h1>Hi, {{user.user.name}}.</h1>
    <h2 class="text-{{user.user.status}}">Your current status: {{user.user.status}}</h2>

    <!-- <input type="text" ng-model="store.user.name" /> -->
    <!-- <input type="text" ng-model="store.user.status" /> -->
</div>
{{user.user.name}} <!-- doesnt't work! -->
```

Note: Break time. Should we have exercises here?
