Vue 兄弟组件通信方法一：事件总线


```
// EventBus.js
import Vue form 'vue';

export const EventBus = new Vue();
```

```
// componentA.vue
mounted() {
  EventBus.$on('eventName', params => {
    // some code here
  }
}
```

```
// compoenntB.vue
methods: {
  onClick() {
    EventBus.$emit('eventName', params);
  }
}
```
