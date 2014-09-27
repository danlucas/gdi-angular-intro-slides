## Adding functionality
```
<div ng-controller="CollectionController as collection">
    <div>
        <h2>
            {{collection.item.name}}
            <span>{{collection.item.release}}</span>
        </h2>
        <h3>International Gross: ${{collection.item.gross}}<h3>
        <div>
            <p>{{collection.item.shortDescription}}</p>
        </div>
        <h3>(In your collection)</h3>
    </div>
</div>
```

Note: Let's say I want to expand my collection to hold movies that I don't own. And wanted to add a little text to the view indicate that
We could add a string to our object and have it display but... nah



## Directives


## NgShow Directive
```
var movie = {
    name: "Marvel's The Avengers",
    gross: 1518.6,
    release: new Date('2012-05-04'),
    shortDescription: 'Superheros destroy city while fighting a Norse god and some aliens',
    inCollection: true
};
```

```
<div ng-controller="CollectionController as collection">
    <div>
        <h2>
            {{collection.item.name}}
            <span>{{collection.item.release}}</span>
        </h2>
        <h3>International Gross: ${{collection.item.gross}}<h3>
        <div>
            <p>{{collection.item.shortDescription}}</p>
        </div>
        <h3 ng-show="{{collection.item.inCollection}}">(In your collection)</h3>
    </div>
</div>
```
<!-- .element: class="fragment" -->


## NgHide Directive
```
var movie = {
    name: "Marvel's The Avengers",
    gross: 1518.6,
    release: new Date('2012-05-04'),
    shortDescription: 'Superheros destroy city while fighting a Norse god and some aliens',
    inCollection: true,
    guiltyPleasure: false
};
```

```
<div ng-controller="CollectionController as collection">
    <div ng-hide="{{!collection.item.guiltyPleasure}}">
        <h2>
            {{collection.item.name}}
            <span>{{collection.item.release}}</span>
        </h2>
        <h3>International Gross: ${{collection.item.gross}}<h3>
        <div>
            <p>{{collection.item.shortDescription}}</p>
        </div>
        <h3 ng-show="{{collection.item.inCollection}}">(In your collection)</h3>
    </div>
</div>
```
<!-- .element: class="fragment" -->

Note: When you want to hide someting when a condition is true
IE. You want to hide your guilty pleasure films



## NgRepeat
```
var movie = {
    name: "Marvel's The Avengers",
    gross: 1518.6,
    release: new Date('2012-05-04'),
    inCollection: true,
    shortDescription: 'Superheros destroy city while fighthing a Norse god and some aliens',
};
```


## NgRepeat
```
var movies = [
    {
        name: "Marvel's The Avengers",
        gross: 1518.6,
        release: new Date('2012-05-04'),
        inCollection: true,
        shortDescription: 'Superheros destroy city while fighthing a Norse god and some aliens',
    },
    {
        name: "Ironman",
        gross: 318.4,
        release: new Date('2008-02-05'),
        inCollection: false,
        shortDescription: 'Billionaire genius invents portable fusion reactor, uses it to build flying suit'
    }
];

```

```
app.controller('CollectionController', function(){
    this.items = movies;
});
```


## NgRepeat
```
<div>
    <h2>
        {{collection.item.name}}
        <span class="small">{{collection.item.release | date:'mediumDate'}}</span>
    </h2>
    <h3>International Gross: {{collection.item.gross * 1000000 | currency:'$'}}<h3>
    <div>
        <p>{{collection.item.shortDescription}}</p>
    </div>
    <h3 ng-show="{{collection.item.inCollection}}">(In your collection)</h3>
</div>
```

Note: Show bad way: collection.item[0].name, etc.


## NgRepeat
```
<div ng-repeat="item in collection.items">
    <h2>
        {{item.name}}
        <span>{{item.release | date:'mediumDate'}}</span>
    </h2>
    <h3>International Gross: {{item.gross * 1000000 | currency:'$'}}<h3>
    <div>
        <p>{{item.shortDescription}}</p>
    </div>
    <h3 ng-show="{{item.inCollection}}">(In your collection)</h3>
</div>
```
Note: show good way
