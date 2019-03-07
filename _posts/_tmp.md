---
title: 2019 月度小结：一月
time: 2019.02.03 22:00:00
layout: post
tags:
- 中文
- 总结
- 感想
series: 2019 月度小结
excerpt: 作为一个三分钟热度的人，我很惊讶地看到有几件事自己居然坚持做了几年——年度小结、读书小结、圣诞明信片。
---

# 《2019 字体日历》

<a href="http://zhangwenli.com/2019-typography-calendar/?ref=blog-0203"><img class="half-img" src="{{ site.loadingImg }}" data-src="{{ site.url }}/img/post/2019-02-03-january-report/website800.png" /></a>这是我在苹果 App Store 上架的第二款 App。

2018 年 12 月 9 日想到的创意，由于 12 月底苹果审核人员放假休息，所以严格来说只有两周左右的时间开发第一版。赶在 12 月 23 日提交的第一版，还是没能赶在元旦前上架，最终于 2019 年 1 月 4 日上架。

我本来比较担心元旦后上架的销量，但是可能因为这个 App 实体版的日历一样，都需要从 1 月 1 日开始撕，所以晚几天买并不亏。

## 销售量及收益

之前的目标销量是一万份。实际一月份卖出了 1 万 6 千多份，不过其中 1 万 2 千多份都是 1 月 24 日生日那天限免「卖」出的……实际收入在 $423 左右，大约￥2852。成本如下：

- 苹果开发者年费（$99）按一半算（因为和另一款 App 平摊）= ￥332
- 字体版权费 $9.99x12 + ￥99x4 = ￥1204

总成本￥1536，盈利￥1316。

设计开发时间大约 100 小时以上，平均时薪 13 元……好吧，做这个本来也不是为了赚钱。只是想着如果项目都是亏本去做的话，可能没有持续的动力，所以 iOS 定价 1 元，至少做到不亏本吧~ 虽然你可以说时间成本也是很大的本，但做这个项目其实是会学到很多东西，所以时间成本是负值都是有可能的。

## 技术相关

想尝试一下「开源但不免费」，所以项目在 GitHub 上开源：[Ovilia/2019-typography-calendar](https://github.com/Ovilia/2019-typography-calendar)。

用到了 ionic 框架，所以开发技术栈还是前端的这些 TypeScript、Angular 等等。由于我在之前的一个应用（牙哈哈心情日记）中用过这个框架，而且很多架构和最佳实践的问题在那个项目中已经探索过了，坑也都踩过了，知道怎么出来了，所以才能做到在两周内做出一个新 App。在这个项目之前，牙哈哈之后，我有尝试过当时还在 Beta 阶段的 ionic 4，发现问题还是比较多，所以这次仍然使用了之前熟悉的 ionic 3。我看到 ionic 在 2019 年 1 月 23 日正式 release 了 4.0 版本，后面的项目可以尝试一下。

另外一个有趣的探索是，怎么解决字体版权不支持内嵌的问题。所谓字体内嵌，是指在 App 或网页中直接引入字体文件，通过 CSS 指定字体。但是，由于一些字体版权不支持内嵌（可能是怕被没有版权的第三方窃取使用），所以只能做成图片的方式使用。

所以我做了一个输入文字、字号、颜色、字体等信息，输出透明背景的图片的 npm 工具 [Ovilia/font2img.js](https://github.com/Ovilia/font2img.js)，也已开源在 GitHub。用这个工具可以非常方便地生成特定字体的图片，对于解决字体内嵌的问题都是通用的，所以我就开源出来了。但是这个库目前还是针对我自己需求做的，如果要做得更通用一些，还是需要再维护一下的。目前的完成度大概在 80% 左右。我觉得在时间很紧的两周内，我还能完成一个（试图）解决通用性问题的工具，这点还是比较难得的。

目前项目的功能以及日历文案都在逐步迭代改进中。我觉得相比纸质的日历而言，这样一本会成长的日历也是很有意思的。

## 安卓发布

由于 ionic 支持跨平台，所以安卓的适配工作只用了短短的两三个小时就完成了。有些不支持的库，如果不是很核心的话（比如撕日历的触摸反馈效果），直接去掉就行了。

但是安卓版的发布很成问题。主要是国内各个应用商店的占比都比较分散平均，可能每个大的应用商店都在 10% 左右的市场份额。这也就算了，比较恶心的一点是，大部分应用商店都强制或以推荐为要挟要求加壳。加壳的意思就是，在我的应用上加一些我也不知道会有什么的功能，增加一些我完全没有用到的隐私权限，并且，还要求以我的名义为此签名。说实话，我都不知道你做了点什么恶心的事，我真的不愿意签这个字。

所以，我在注册了好多应用商店的开发者账号后，最终选择直接将 apk 文件部署在我自己的开发机上。至今总下载量在 2600 左右，相比 iOS 是少很多了。

而之所以没部署在 Google Play，主要是考虑到这个 App 是只有中文版的，而 Google Play 在国内市场份额非常少，$49 的年费看起来是完全回不了本的……当然，作为一项成就，我觉得下次开发包含非中文语音的 App，并且不像牙哈哈这么小众的话，我很愿意考虑一下 Google Play 的。

## 用户反馈


