学习链接：[You Don't Know JS](https://github.com/getify/You-Dont-Know-JS/blob/1st-ed/this%20%26%20object%20prototypes/ch5.md)

1.原型继承其实叫做“委托”比较合适，因为“继承”一般是相对于类和类来说，而JS中其实是不存在“类”的，只有对象，而且，原型继承不是把属性和方法复制到实例中，而是通过.prototype来链接

2.对于以下代码：

```javascript
function Foo(name) {
  this.name = name;
}

Foo.prototype.my = function() {
  return this.name;
}

function Bar(name, label) {
  Foo.call(this, name);
  this.label = label;
}

Bar.prototype = Foo.prototype;
```

`Bar.prototype = Foo.prototype` 这种写法并不好，因为`Bar.prototype`和`Foo.prototype`指向同一个对象，如果改了那个对象，所有实例都会被影响到。

`Bar.prototype = new Foo()` 这种方法虽然得到了一个新对象，但是也不好，因为Foo函数如果存在副作用，new Foo()就会执行副作用。

正确做法应该是`Bar.prototype = Object.create(Foo.prototype)`。

或者，更进一步：

```javascript
Bar.prototype = Object.create(Foo.prototype, {
  constructor: {
    value: Bar,
    writable: true,
    configurable: true,
    enumerable: false
  }
})
```

将`Bar`的`prototype.constructor`指向自己。
