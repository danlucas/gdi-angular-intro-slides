## Filters
Let's clean up that [date](https://docs.angularjs.org/api/ng/filter/date)
```
<div ng-controller="CollectionController as collection">
    <div>
        <h2>
            {{collection.item.name}}
            <span>{{collection.item.release | date:'mediumDate'}}</span>
        </h2>
        <h3>International Gross: ${{collection.item.gross}}<h3>
        <div>
            <p>{{collection.item.shortDescription}}</p>
        </div>
    </div>
</div>
```

Note:
- Well that's all nice but what's with that date, tho?
sample custom filter
myApp.filter('reverse', function () {
  return function (text) {
    return text.split("").reverse().join("");
  }
});


## Filters
And the revenue
```
<div ng-controller="CollectionController as collection">
    <div>
        <h2>
            {{collection.item.name}}
            <span>{{collection.item.release | date:'mediumDate'}}</span>
        </h2>
        <h3>International Gross: ${{collection.item.gross * 1000000 | currency:'$' }}<h3>
        <div>
            <p>{{collection.item.shortDescription}}</p>
        </div>
    </div>
</div>
```


## More Built-in Filters
[https://docs.angularjs.org/api/ng/filter](https://docs.angularjs.org/api/ng/filter)
