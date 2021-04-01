LCP: Largest Contentful Paint
指的是页面中尺寸最大（指的是宽高度）的元素绘制完成的时间。
这是一个迭代的过程，页面在加载过程中，当前的最大元素有可能在加载了其他元素之后就不再是最大了，
因此如果有更大的元素出现，最大元素就会被替换为更大的元素；但是如果最大元素被移除了，最大元素不会被替换，除非有更大元素出现。

图片有些需注意地方，see [https://web.dev/uses-optimized-images/](https://web.dev/uses-optimized-images/)
