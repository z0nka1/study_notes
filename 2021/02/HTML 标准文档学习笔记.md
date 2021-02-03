1. 一个事件循环（event loop）有一个或多个任务队列（task queue）
2. 任务队列是有序集（ordered set），不是队列（queue）
3. 微任务队列不是队列（原话：The microtask queue is not a task queue.）
4. 每个事件循环有一个微任务队列
5. 每个事件循环有一个标记是否正在执行微任务检查点（microtask checkpoint）的开关
