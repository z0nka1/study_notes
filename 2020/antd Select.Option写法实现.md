## antd Select.Option

antd 用了很久了，一直很好奇`Select.Option`这种写法是怎么实现的，于是去github仓库翻看了源码，发现在`index.tsx`里面是用了静态属性`static Option = Option`，就这么简单？！

这样做的好处是，当我们 import Select 的时候，就可以直接用 Select.Option 了，免去了另外 import Option 的麻烦。

不过可能我的理解还比较初级和片面！
