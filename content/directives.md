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
    </div>
</div>
```

Note: Let's say I want to expand my collection to hold movies that I don't own.


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

Note: And wanted to add a little text to the view indicate that
We could add a string to our object and have it display but... nah


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



Only show when you actually own it... <!-- .element: class="fragment" -->
note: Enable user to show and hide a longer description
