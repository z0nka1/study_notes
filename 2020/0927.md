1.ES6 的class也没有像传统的面向类语言那样在声明时拷贝方法，很大程度上也是`[[Prototype]]`机制的语法糖，所以在“父类”上更改/替换一个方法，“子类”或者实例也会受到影响。


```javascript
class C {
	constructor() {
		this.num = Math.random();
	}
	rand() {
		console.log( "Random: " + this.num );
	}
}

var c1 = new C();
c1.rand(); // "Random: 0.4324299..."

C.prototype.rand = function() {
	console.log( "Random: " + Math.round( this.num * 1000 ));
};

var c2 = new C();
c2.rand(); // "Random: 867"

c1.rand(); // "Random: 432" -- oops!!!
```
