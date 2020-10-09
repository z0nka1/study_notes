### new 操作符

1. 构造函数`return`原始数据类型的值（比如字符串、数字），`new`操作符不受影响

```
function Test(name) {
	this.name = name
	return 26
}
const t = new Test('Kitty')
console.log(t) // { name: 'Kitty' }
console.log(t.name) // 'Kitty'
```


2. 如果`return`对象类型的值（这里的对象是广义上的对象，包括数组、函数、Date、RegExp等），那么`new`后等到`return`的那个值

```
function Test(name) {
	this.name = name
	return [1,2]
}
const t = new Test('Kitty')
console.log(t) // [1,2]
console.log(t.name) // undefined
```


### forEach 内部不支持await
