# JavaScript in basic

> [3 ways to define a JavaScript class](https://www.phpied.com/3-ways-to-define-a-javascript-class/)

#### 1. Cookies

> cookies are data, stored in small text files, in web pages.

```js
// create a cookie, add expire date(UTC time), cookie belongs to current page
document.cookie = "username=John Smith; expires=Thu, 18 Dec 2017 12:00:00 UTC; path=/";

// read a cookie, will return all cookies in one string
var x = document.cookie;

// to delete a cookie just set the expires parament to a passed date
```

usage:

```js
function setCookie(name, value, exdays) {
    var date = new Date();
    date.setTime(date.getTime() + (exdays*24*60*60*1000));
    var expires = "expires=" + date.toUTCString();
    document.cookie = name + "=" + value + ";" + expires + ";path=/";
}

function getCookie(name) {
    var name = name + "=";
    var decodedCookie = decodeURIComponent(document.cookie);
    // split cookies into an array
    var cookies = decodedCookie.split(';');
    for (var i = 0; i < cookies.length; i++) {
        var c = cookies[i];
        while (c.charAt(0) == ' ') {
            c = c.substring(1);
        }
        if (c.indexOf(name) == 0) {
            return c.substring(name.length, c.length);
        }
    }
    return "";
}

function checkCookie() {
    var username = getCookie("username");
    if (username != "") {
        alert("welcome again " + username);
    } else {
        username = prompt("Please enter your name:", "");
        if (usrname != "" && username != null) {
            setCookie("username", username, 365);
        }
    }
}
```

[The Difference Between URLs and URIs](https://danielmiessler.com/study/url-uri/)

#### 2. Date Methods

> date methods can get and set date values(years, months, days, hours, minutes, seconds, millisecondes)

Date Formats:
as a string `Wed Nov 01 2017 10:41:22 GMT+0800 (CST)`
as a number `1509504082258`

```js
// create a new date object with the current date and time
var date = new Date();

// create a new date object from the specified date and time
var date = new Date("October 13, 2014 11:13:00");

// create a new date object as zero time plus the number
var date = new Date(86400000);

// create a new date object with the specified date and time
var date = new Date(99, 5, 24, 11, 33, 30, 0);
```

Dispalying Dates:
```js
date.toString();    // Wed Nov 01 2017 10:57:12 GMT+0800 (CST)
date.toUTCString();    // Wed, 01 Nov 2017 02:57:22 GMT
date.toDateString();   // Wed Nov 01 2017

date.toLocaleString();   // Converts a Date object to a string, using locale conventions
```

setDate() method can be used to add days to a date:
```js
var date = new Date();
date.setDate(date.getDate() + 30);
```

#### 3. this

> [Understand JavaScript’s “this” With Clarity, and Master It](http://javascriptissexy.com/understand-javascripts-this-with-clarity-and-master-it/)

```js
var user = {
    tournament: 'The Masters',
    data: [
        {name: "T.Woods", age: 37},
        {name: "P.Mickelson", age: 43}
    ],
    clickHandler: function(event) {
        var _this = this;
        this.data.forEach(function(person) {
            console.log(person.name + "is playing at" + _this.tournament);
            })
    }
}
```

#### 4. forEach() method

> forEach() executes the provided `callback` once for each element present in the array in ascending order.

```js
arr.forEach(function callback(currentValue, index, array) {
    //your iterator
}[, thisArg]);
```

```js
var arr = ['a', 'b', 'c'];

arr.forEach(function(element){
    console.log(element);
    });
```
[The for Loop vs. forEach in JavaScript](https://thejsguy.com/2016/07/30/javascript-for-loop-vs-array-foreach.html)

#### 5. Objects in Detail

> objects can contain any other data type, including Numbers, Arrays, and even other Objects.

```js
var person = {name: "Kobe"};
// copy the person object not an actual value
var anotherPerson = person;
person.name = "Bryant";

console.log(anotherPerson.name);   // Bryant
console.log(person.name);    // Bryant
```

Object Constructor:
```js
var mango = new Object();
mango.color = "yellow";
mango.shape = "round";

mango.howSweetAmI = function() {
    console.log("Hmm Hmm Good");
}
```

1) Constructor Pattern for Creating Objects

```js
function Fruit(name, color, native) {
    this.name = name;
    this.color = color;
    this.native = native;

    this.showName = function() {
        console.log("This is a " + this.name);
    }

    this.nativeTo = function() {
        this.native.forEach(function(eachCountry) {
            console.log("Grown in: " + eachCountry);
            });
    }
}

// usage
var mango = new Fruit("Mango", "yellow", ["US", "CN", "PH"]);
mango.showName();   // This is a Mango
mango.nativeTo();
```

2) Prototype Pattern for Creating Objects

```js
function Fruit() {
}
Fruit.prototype.name = "Generic Fruit";
...
```

[JavaScript Objects in Detail](http://javascriptissexy.com/javascript-objects-in-detail/)
