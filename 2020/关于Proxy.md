### Proxy 学习

语法：const proxyObject = new Proxy(target, handler);

target可以是任意类型的对象，包括数组、函数等。

handler是一个包含traps（捕获器））的对象。

通过在target外面包装一层，达到对作用于target的操作进行拦截然后自定义。

例子：

```javascript
const person = {
  firstName: 'Trump',
  lastName: 'Donald'
}

const proxyPerson = new Proxy(person, {
  get: function(target, property) {
    if (property === 'fullName') {
      return `${target.firstName} ${target.lastName}`;
    }
    return target[property];
  }
})

console.log(person.firstName); // Trump

// 没有fullName属性，但是我们在proxy内部做了处理
console.log(person.fullName); // Trump Donald
```
