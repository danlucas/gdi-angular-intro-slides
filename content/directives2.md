## More Directives



## While you were gone
```
{
    name: "Marvel's The Avengers",
    gross: 1518.6,
    release: new Date('2012-05-04'),
    inCollection: true,
    shortDescription: 'Superheros destroy city while fighthing a Norse god and some aliensl',
    actors: [
        "Robert Downey, Jr.",
        "Chris Hemsworth",
        "Chris Evans",
        "Jeremy Renner",
        "Mark Ruffalo",
        "Scarlett Johansson",
        ...
    ],
    longDescription: "Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
}
```

Note:
we added some more data!
Let's display but now with tabs!


## Add Tabs
```html
<section>
    <ul class='nav nav-tabs'>
        <li><a href>Description</a></li>
        <li><a href>Cast</a></li>
    </ul>
</section>
```


## ngclick
```
<section>
    <ul class='nav nav-tabs'>
        <li><a href ng-click="tab = 1">Description</a></li>
        <li><a href ng-click="tab = 2">Cast</a></li>
    </ul>
    {{tab}}
</section>
```

Note:
ng-click is a new directive
when clicking on it, it takes an action (in this case changing the value of tab)


## Add panels
```
<section>
    <ul class='nav nav-tabs'>
    ...
    <div class="panel" ng-show="tab === 1">
        <h4>Description</h4>
        <blockquote>{{item.longDescription}}</blockquote>
    </div>
    <div class="panel" ng-show="tab === 2">
        <h4>Cast</h4>
        <table class='table'>
            <tr ng-repeat="member in item.cast">
                <td>{{member.name}}</td>
                <td>{{member.character}}</td>
            </tr>
        </table>
    </div>
</section>
```

Note:
using ng-show to test the value of tab


### nginit
Set an initial tab value
```
<section ng-init="tab=1">
```
Note:
Sets a value when loaded


### ngclass
Set the active tab
```
<ul class='nav nav-tabs'>
    <li ng-class="{active:tab === 1}"><a href ng-click="tab = 1">Description</a></li>
    <li ng-class="{active:tab === 2}"><a href ng-click="tab = 2">Cast</a></li>
</ul>
```
Note:
Sets a dynamic class based on a value



### This is starting to look a little ugly...
```
<section ng-init="tab=1">
    <ul class='nav nav-tabs'>
        <li ng-class="{active:tab === 1}"><a href ng-click="tab = 1">Description</a></li>
        <li ng-class="{active:tab === 2}"><a href ng-click="tab = 2">Cast</a></li>
    </ul>

    <div class="panel" ng-show="tab === 1">
        <h4>Description</h4>
        <blockquote>{{item.longDescription}}</blockquote>
    </div>
    <div class="panel" ng-show="tab === 2">
        <h4>Cast</h4>
        <table class='table'>
            <tr ng-repeat="member in item.cast">
                <td>{{member.name}}</td>
                <td>{{member.character}}</td>
            </tr>
        </table>
    </div>
</section>
```


### Move the logic into the controller
```
<section ng-controller="PanelController as panel">
    <ul class='nav nav-tabs'>
        <li ng-class="{active:panel.isTabSelected(1)}"><a href ng-click="panel.selectTab(1)">Description</a></li>
        <li ng-class="{active:panel.isTabSelected(2)}"><a href ng-click="panel.selectTab(2)">Cast</a></li>
    </ul>

    <div class="panel" ng-show="panel.isTabSelected(1)">
        <h4>Description</h4>
        <blockquote>{{item.longDescription}}</blockquote>
    </div>
    <div class="panel" ng-show="panel.isTabSelected(2)">
        <h4>Cast</h4>
        <table class='table'>
            <tr ng-repeat="member in item.cast">
                <td>{{member.name}}</td>
                <td>{{member.character}}</td>
            </tr>
        </table>
    </div>
</section>
```


### Move the logic into the controller
```
app.controller('PanelController', function(){
    this.tab = 1;

    this.selectTab = function(setTab){
        this.tab = setTab;
    };

    this.isTabSelected = function(checkTab){
        return this.tab === checkTab;
    };
});
```
