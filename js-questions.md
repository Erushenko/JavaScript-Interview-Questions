# JavaScript Interview Questions

___

## 1

``` js
(function(){
  var a = b = 3;
})();

console.log("a defined? " + (typeof a !== 'undefined'));
console.log("b defined? " + (typeof b !== 'undefined'));
```

>a defined? false
>
>b defined? true

## 2

``` js
var myObject = {
  foo: "bar",
  func: function() {
    var self = this;
    console.log("outer func:  this.foo = " + this.foo);
    console.log("outer func:  self.foo = " + self.foo);
    (function() {
      console.log("inner func:  this.foo = " + this.foo);
      console.log("inner func:  self.foo = " + self.foo);
    }());
  }
};
myObject.func();
```

>outer func:  this.foo = bar
>
>outer func:  self.foo = bar
>
>inner func:  this.foo = undefined
>
>inner func:  self.foo = bar

## 3

``` js
function foo1()
{
  return {
    bar: 'hello'
  };
}

function foo2()
{
  return
  {
    bar: 'hello'
  };
}
console.log('foo1 returns: ' + foo1())
console.log('foo2 returns: ' + foo2())
```

>foo1 returns: { bar: 'hello'}
>
>foo2 returns: undefined

## quicksort

``` js
function binary_search(arr, el) {
  let high = arr.length - 1
  let low = 0
  while (low <= high) {
    const mid = Math.ceil((low + high)/2)
    console.log(low, high, mid);
    guess = arr[mid]
    if (guess == el) {
      return mid
    }
    if (guess > el) {
      high = mid - 1
    } else {
      low = mid + 1
    }
  }
  return -1
}

console.log(binary_search([1, 2, 3, 4, 5, 6, 7, 8, 9], 7));
console.log(binary_search([1, 2, 3, 4, 5, 6, 7, 8, 9], 8));
console.log(binary_search([1, 2, 3, 4, 5, 6, 7, 8, 9], 9));
```
