### Yeah that's still kind of ugly
- Our app is hard to read
- And some of these parts could be reusable

Note:
It's really not clear what's happening for one thing
It's not reusable


## Let's make our own directive
In our HTML
```
<item-title></item-title>
```

In our app
```
app.directive('itemTitle', function(){
    return{
        restrict: 'E',
        templateUrl: 'templates/item-title.html'
    };
});
```

In our template
```html
{{item.name}}
<span class="small">{{item.release | date:'mediumDate'}}</span>
```


## Restrict

```
app.directive('itemTitle', function(){
    return{
        restrict: 'E',
        templateUrl: 'templates/item-title.html'
    };
});
```
`restrict` is the type of directive this code will match

A: attribute
```
<div item-title></div>
```

E: element
```
<item-title></item-title>
```

C: class
```
<div class="item-title"></div>
```

Note:
You'd use element more for UI widgets
Attributes for mixins (decorating existing stuff), like turning a block of text into a tool tip.
You can even do multiple so that they all work.



### Directives with Controllers


### Let's move those panels

In our HTML
```
<item-panels>
</item>
```

In our app
```
app.directive('itemPanels', function(){
    return{
        restrict: 'E',
        templateUrl: 'templates/item-panels.html'
    };
});
```

In our template
```html
<ul class='nav nav-tabs'>
...
</ul>
<div class="panel" ng-show="panel.isTabSelected(1)">
...
</div>
<div class="panel" ng-show="panel.isTabSelected(2)">
...
</div>
```


### Now we need to move the controller into the directive
```
app.directive('itemPanels', function(){
    return{
        restrict: 'E',
        templateUrl: 'templates/item-panels.html',
        controller: function(){
            this.tab = 1;

            this.selectTab = function(setTab){
                this.tab = setTab;
            };

            this.isTabSelected = function(checkTab){
                return this.tab === checkTab;
            };
        },
        controllerAs: 'panels'
    };
});
```
