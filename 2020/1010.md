### 模拟实现new操作符

```
function create() {
  let obj = {};
  // 通过借用数组的方法，获得第一个参数（即构造函数），并删除arguments的第一个参数
  let constructor = [].shift.call(arguments);
  // 将obj的原型设为构造函数的prototype属性
  Object.setPrototypeOf(obj, constructor.prototype);
  // 将obj作为上下文调用构造函数
  let ret = constructor.apply(obj, arguments);
  return ret instanceof Object ? ret : obj;
}
const p = create(Person, 'firstName', 'lastName');
```
