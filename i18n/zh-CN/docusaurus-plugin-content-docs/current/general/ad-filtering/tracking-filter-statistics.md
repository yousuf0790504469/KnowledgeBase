---
title: 跟踪过滤规则统计
sidebar_position: 4
---

:::note

「*发送广告过滤器使用情况*」选项默认是禁用的。 除非用户手动开启该选项以帮助我们改进拦截过滤器，软件什么信息也不会发送。

:::

### 为什么广告过滤器很重要？

让我们先从广告过滤器的定义开始。 有了广告过滤器的帮助，AdGuard 才能移除网站上的广告。 它们是基于用户对网站广告的投诉而手动编译的。 广告过滤器是 AdGuard 的重要元素，它们的品质确定 AdGuard 拦截广告的整体效果。

然而，有个缺点。 Over the years, more and more ad filters have appeared. The more ad filters there are, the more memory AdGuard consumes, thus slowing down the rendering of webpages. At the same time, some filters expire and gradually become useless, consuming memory and slowing down the program.

### 为什么统计数据很重要？

我们希望一劳永逸地解决过滤规则过期的问题。 不过，我们需要大家的帮助。 收集使用的过滤规则的统计数据，让我们检测并移除不再使用的规则。 结果，我们能帮助安装 AdGuard 的新用户。

如果用户有一台足够强大的计算机，本问题就不会真正影响他。 不过，对于低功耗笔记本电脑和平板电脑的用户来说，差异将非常明显。

### 统计数据包括什么信息？

如用户开启「*发送广告过滤器使用情况*」，软件将定期发送以下信息：

- 扩展版本
- 浏览器类型（Chrome/Firefox/Opera/Yandex.Browser/Safari）
- 启用的广告过滤器列表
- 列表由以下元素组成：
    - *网站域名*
    - *最近的页面浏览量*
    - *在网站上激活的过滤规则和过滤器 ID 的列表*
    - 「*被阻止发送请求至URL的域名规则*」 该列表是根据网站自上次发送统计数据以来的访问统计数据创建的

收集的统计数据将定期发送到我们的服务器以便我们分析和优化过滤器。

请注意，我们获得的所有统计数据都是平均且匿名处理的。 我们不会将统计数据用作除优化过滤器之外的其它用途，我们也不会销售它们给第三方。 用户可以在我们的[隐私政策](https://adguard.com/privacy.html)中阅读相关内容。

### 跟踪过滤规则统计会导致什么？

对于绝大多数用户来说，电脑速度的变化其实并不明显。 不过，上网本和平板电脑用户可能会注意到速度略有放缓。

我们将定期向服务器发送收集到的统计数据。 传输的数据大小不是很大，与普通网页的大小相当。
