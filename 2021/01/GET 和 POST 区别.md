广义上来说，GET 和 POST 都是 TCP 连接，本质上并无差别。

以下列出他们之间的一些表面上的区别：

1. 语义不同，GET 主要用于获取数据，POST 主要用于产生副作用的情景
2. 数据传递方式不同，GET 直接在URL传参，而 POST 在 request body 传参。但是，这只是习惯用法，GET 方法用 request body 传参在技术上完全可行
3. GET 可以被浏览器主动缓存，而 POST 不会
4. GET 会产生1个 TCP 数据包，而 POST 会产生2个。但也不是绝对，Firefox 就只会产生一个
5. GET 只能进行 URL 编码，POST 有多种编码方式
6. GET 在浏览器回退时不会重新发送请求，而 POST 会
7. GET 请求参数会保留在浏览器历史，而 POST 不会
8. 对于参数数据类型，GET 只接受 ASCII 码，POST 没有限制

关于第4点，GET 请求会一次性把 header 和 data 一起发送，而 POST 请求会先发送 header，服务器响应100 continue，客户端再发送data。
