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
    var app = angular.module('collection', [ ]);

    app.controller('UserController', function($scope){

    });
})();
```



## Controllers
Then assign the data to a property
```
(function(){
    var app = angular.module('collection', [ ]);

    app.controller('UserController', function($scope){
        $scope.user = user;
    });

    var user = {
        name: 'Dan Lucas',
        status: 'primary'
    };
})();
```



## Attaching the Controller
```
<div class="container" ng-controller="UserController">
    <h1>Hi, {{user.name}}.</h1>
    <h2 class="text-{{user.status}}">Your current status: {{user.status}}</h2>

    <!-- <input type="text" ng-model="user.name" /> -->
    <!-- <input type="text" ng-model="user.status" /> -->
</div>
```



## Understanding Scope
The "scope" of the controller only works inside of the container

```
<div class="container" ng-controller="UserController">
    <h1>Hi, {{user.name}}.</h1>
    <h2 class="text-{{user.status}}">Your current status: {{user.status}}</h2>

    <!-- <input type="text" ng-model="user.name" /> -->
    <!-- <input type="text" ng-model="user.status" /> -->
</div>
{{user.name}} <!-- doesnt't work! -->
```

Note: Exercise time. Set up new collection to be used with the rest of the class.
