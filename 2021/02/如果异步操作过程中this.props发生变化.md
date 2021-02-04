如果异步操作过程中this.props发生变化，且异步操作的结果依赖于this.props，结果可能与预期不符。

例如，有一个post列表，可以点击一个like按钮，但在发送like请求之前，需要先确认是否可以like，这会消耗一些时间。
在这过程中（确认是否可以like还未完成）切换了post，因此在确认完成后发送的like请求实际上带上了当前的post，而非点击like按钮的那个post。

see：[https://epicreact.dev/how-react-uses-closures-to-avoid-bugs](https://epicreact.dev/how-react-uses-closures-to-avoid-bugs)
