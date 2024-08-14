# 一些 CSS 问题

## px、em 还是 rem ？媒体查询中断点的单位该如何选择？

前言

关于 \<html> 的 font-size：

```
html {
    font-size: 62.5%；
    // 定义了 em 和 rem 的大小：16px * 62.5% = 10px
    // 其中 16px 是浏览器默认字体大小
}
```

以上的字体CSS，结合 rem 为单位，让用户可以通过修改浏览器默认字体大小，从而影响页面内容大小

问题

媒体查询中断点的单位是否也使用 rem ？还是使用 em 或 px ？

测试

断点单位分别使用 px，em，rem ，并基于以下三种场景进行测试（详见 [PX, EM or REM Media Queries?](https://zellwk.com/blog/media-query-units/)）

1. 改变 \<html> 的 font-size
2. 用户缩放页面
3. 用户更改浏览器默认字体大小设置

测试结果

1. rem 在 safari 中出现问题
2. safari 中，px 和 rem em 的结果不同（可能 safari 缩放页面时会改变浏览器默认字体大小）
3. rem em 的断点会随浏览器字体大小变化，px 的保持初始值

讨论

- 由于 rem 在 safari 中奇怪的表现，毫无疑问，我们不能使用 rem 当作断点的单位
- em 的真实值会随着浏览器字体大小改变，断点不再有一个确定值，可能会出现以下情况：在同样大小的设备上会出现两种不同的布局（一个用户设置较大的字体，一个用户设置较小的字体，这样会导致产生不同的断点），这种情况有些背离了媒体查询的初衷（根据屏幕大小改变页面布局）
- px 是一个绝对单位，这表示一切都是固定的，缺点是没有尊重用户更改字体大小的设置（但是有些时候页面布局发生的变化，这真的是用户在设置字体大小时想要的吗？），并且，在 [List of most-visited websites](https://en.wikipedia.org/wiki/List_of_most-visited_websites) 中，主流网站大部分都在使用 px，px 是被大厂所认可的

总结

- 使用 px，对于开发者来说，使用固定的断点，更加清晰
- 使用 em，尊重了用户改变浏览器字体大小的设置
- 使用这两种方式都可以，个人倾向于使用 px

参考

- [PX, EM or REM Media Queries?](https://zellwk.com/blog/media-query-units/)
- [Switching to Em-Based Media Queries](https://stackoverflow.com/questions/22228568/switching-to-em-based-media-queries)
- [To em or not to em? That is the media query question.](https://medium.com/zoosk-engineering/to-em-or-not-to-em-that-is-the-media-query-question-22f4a65e9747)