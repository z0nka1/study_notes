```
<body>
<script src='xxx' />
<div>上面的JS加载并执行完成后才会出现在页面</div>
```

如果加上`defer`或者`async`：

```
<body>
<script defer src='xxx' />
<div>HTML解析后立即出现在页面，不用等待上面的JS加载</div>
```

defer、async区别：

1. 多个defer的脚本同时存在，不管哪个先加载完成，执行顺序都是按文档顺序；async则是哪个先加载完成就先执行哪个
2. defer一定在 DOMContentLoaded 事件之前执行，async与 DOMContentLoaded 没关系，有可能在其之前，也有可能在其之后
