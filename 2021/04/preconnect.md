对于关键请求，应使用preconnect：

```
<link rel='preconnect' href='xxx.com' />
```

跨域请求还应加上crossorigin：

```
<link rel='preconnect' href='xxx.com' crossorigin />
```

为了兼容性更好，还应配合使用dns-prefetch：

```
<link rel='preconnect' href='xxx.com'>
<link rel='dns-prefetch' href='xxx.com'>
```

source: [https://web.dev/uses-rel-preconnect/](https://web.dev/uses-rel-preconnect/)
