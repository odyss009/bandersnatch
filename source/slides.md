% Modern Frontend Development Workflow
% joe
% 2013/11/04

# HTML

## basic
* contents
* basic structure

##
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    </head>
    <body>
        <h1>Hello World</h1>
    </body>
    </html>

# CSS

## position

* static
* relative
* absolute

## display

* block
div
* inline
span
* float
* none

## visibility

* hidden

## selector

* ID
* class
* element
* child
* attr
* child, descendant, sibling, pseudo
* [reference](https://developer.mozilla.org/en-US/learn/css)

## layout
* fixed
* fluid

# CSS3 and more
* transition
* transform
* H/W acceleration
* [sample](http://famo.us/)

# DOM

##
* messy

##
    var elem = document.createElemeent("div");
    docuemnt.childNodes.firstChild.appendChild(elem);

# Event Model
* cross browsing
* event bubbling/capturing
* event delegation

# jQuery

## selector engine

    $("#service").html("blabla");
    $(".service").css({
        color : "red"
    });
    $("input[name=pass]").val("blabla");

## chain

    $("#service")
    .html("blabla")
    .css("color", "red")

## plugin
* jquery UI
* community
* [jqueyr boilerplate](http://jqueryboilerplate.com/)

# javascript

## feature

* high order function
* closure
* dynamic
* prototype
* literal
* single thread
* call, apply
* async

## create pattern

    var obj = {};
    var arr = [];
    var Animal = function() {
        this.name = "meerkat";
        this.legs = 4;
    };
    var someAnimal = new Animal();

## create pattern2

    var newObj = Object.create({ name : 'joe'});

## extend pattern

    var child = $.extend(target, source1, source2);
    var newChild = $.extend(true, target, source1, source2);

## call and apply

    var Cat = function(name) {
        this.name = name;
    };
    Cat.prototype.meow = function(food) {
        alert(this.name + " " + food);
    }
    var cat = new Cat();

    var obj = { name : "tiger" };
    cat.meow.call(obj, "food1");
    cat.meow.apply(obj, ["food1"]);

## high order function1

* curry - bind

## bind

    function callback(arg1, arg2) {
        //blabla
    }

    function someFunc(callback) {
        callback("arg2");
    }

    someFunc(callback.bind("arg1"));

## async1

    setTimeout(function() {
        alert('timeout');
    }, 3000);

## async2

    somefunc(function(cb1) {
        cb1(function(cb2) {
            cb2(function() {
                //blabla...
            });
        });
    });

## deferred and promise1

    $.ajax("someurl")
      .done(function(data) {
          alert("success");
       });
     .fail(function() {
          alert("success");
      });
     .always(function() {
          alert("always");
      });

    $.ajax("anotherUrl")
      .then(function () {
          alert("success");
      }, function() {
          alert("error");
      });

## deferred and promise2

    var ajax1 = $.ajax("url1");
    var ajax2 = $.ajax("url2");

    $.when(ajax1, ajax2)
     .done(function(data) {
         alert("success");
     });

## deferred and promise3

    $.ajax("anotherUrl")
      .then(function (data) {
          return anotherDeferred(data);
      })
      .then(function (data) {
          //alert(data);
      })

## deferred and promise4

    var ajax1 = $.ajax("url1");
    var ajax2 = $.ajax("url2");
    var aggre1 = $.when(ajax1, ajax2);
    var ajax3 = $.ajax("url3");
    var ajax4 = $.ajax("url4");
    var aggre2 = $.when(ajax3, ajax4);

    $.when(aggre1, aggre2)
     .done(function(data) {});

## deferred and promise4

    function elegantFunc() {
        var dfd = $.Deferred();

        setTimeout(function () {
            if(status) {
                dfd.resolve(); 
            } else {
                dfd.reject();
            }
        }, 3000);

        return dfd;
    }

    elegantFunc().done(function() {});

## cons

* global
* var
* function scope
* implicit type conversion(==, !=)

## solution

* strict mode
* jshint
* module pattern

## Best Friend

* [lodash](http://lodash.com/)
* [Q](https://github.com/kriskowal/q)
* [requrieJS](http://requirejs.org/docs/start.html)
* commonJS - [browserify](http://browserify.org/)

## Transpiler

* [coffeescript](http://coffeescript.org/)
* [TypeScript](http://www.typescriptlang.org/)
* [clojurescript](https://github.com/clojure/clojurescript)
* [google traceur](https://code.google.com/p/traceur-compiler/)
* [sourcemap](http://www.html5rocks.com/en/tutorials/developertools/sourcemaps/)

## ECMA6

* Iterator
* Generator
* let
* module, class

## HTML5

* local storage
* session storage
* indexedDB
* websocket
* canvas
* SVG
* WEBGL
* WebRTC

# bootstrap

* clean markup
* layout
* css module
* support responsive
* jquery widget

# build & package management
* [grunt](http://gruntjs.com/)
* [yeoman](http://yeoman.io/)
* [bower](http://bower.io/)

# Inspector
* [Chomme DevTools](https://developers.google.com/chrome-developer-tools/)
* network monitoring
* profiling
* debugging
* development tool
* console

# SPA - single page application

* web application like gmail
* manage state in the client side
* dependency
* routing
* template engine
* MVC, MVVM
* mediator
* application life cycle
* SEO - [phantomjs](http://phantomjs.org/)

# Popular Framework
* [Backbone](http://backbonejs.org/)
* [Ember](http://emberjs.com/)
* [Angular](http://angularjs.org/)

# AngularJS

* mady by google
* dependency injection
* two way binding
* MVW
* declarative - web component
* dirty checking
* scope

# End
next time
