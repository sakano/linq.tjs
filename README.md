# linq.tjs

LINQ for TJS

## Installation
Put following files into your project folder.
* linq.tjs
* linq_generate.tjs
* linq_order.tjs
* linq_utility.tjs

Then load linq.tjs.
```
Scripts.execStorage("linq.tjs");
```

## Example
```
var data = [
    %[ name : "United States",  GDP:17348072 ],
    %[ name : "China",          GDP:10430590 ],
    %[ name : "Japan",          GDP:4605511 ],
    %[ name : "Germany",        GDP:3868291 ],
    %[ name : "United Kingdom", GDP:2988893 ],
    %[ name : "France",         GDP:2829192 ],
    %[ name : "Brazil",         GDP:2346523 ],
    %[ name : "India",          GDP:2054941 ]
];

// print countries' name whose GDP is greater than 3000000
Enumerable.from(data)
    .where(function(x) { return x.GDP > 3000000; })
    .select(function(x) { return x.name; })
    .forEach(function(name) { Debug.message("name: " + name); });

// Above code will output :
//   name: United States
//   name: China
//   name: Japan
//   name: Germany

// string can be used as function expression
Enumerable.from(data)
    .where("_.GDP > 3000000")
    .select("_.name")
    .forEach("Debug.message('name: ' + _)");
```
