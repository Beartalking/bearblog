---
title: "我是如何做出一个失败的小程序的？"
datePublished: Mon Mar 06 2017 11:00:00 GMT+0000 (Coordinated Universal Time)
cuid: cl2vn4qjy030ku5nvc98jb4jb
slug: a-failed-wechat-app
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1651914278930/UMbSoKFgi.jpg

---

![connet everything](http://i.imgur.com/AVt9BTk.jpg)

到底小程序可以怎么玩？现在做小程序还晚吗？让真正做过的人告诉你吧！<!-- more -->

现在讲关于微信小程序的分析文章，至少有 95% 的作者最多只玩过几个小程序，没有开发经验；5% 的实践者里，大约又有 10% 的小程序取得了很好的推广效果，有着持续增长的用户，也可能会有着其他的机会。

而我，是这 5% 里的另外那 90%：**我做了一款小程序，但是失败了。**

我会在这篇文章里分享一下我们制作小程序的一些经验。这事儿没有做 app 那么难，但也不算很容易。了解了我是如何失败的，也许当你在实际要自己操作的时候，也就可以少走一些弯路。至少，别听那些水都没下过就谈游泳的，听听真正尝试过的人的经验，才是有价值的干货。

到底小程序可以怎么玩？现在做小程序还晚吗？让真正做过的人告诉你吧！

![2017-03-07_miniapp-01](http://i.imgur.com/cgSjffJ.jpg)

## “狗熊月读”小程序的诞生与失败
最初的故事大家都知道，2016 年年底，因为微信张小龙的一次演讲，微信小程序的概念为大家所知，于是很多团队都开始准备着，在这个非常新锐的领域探索一番。

我和两位技术的小伙伴：从事 iOS 开发的 K，与从事 Web 开发的 J 三人一起，组成了一个讨论组，大家都觉得小程序是一个很有意思的平台，但具体要做些什么，我们还没有想好。

当时我提议，我的付费会员读书分享群 “狗熊月读” 已经有了现成的内容和会员，但一直缺乏一个可以让会员在其中收听、收看音视频内容，查看会员资料的移动端平台，不如我们用小程序的平台来做一下测试？顺便也摸索一下这种开发是否可行。大家都觉得这种思路 OK。于是，11 月下旬，我注册了小程序开发者的身份，并用自己的公司作为认证主体，完成了微信认证。

这段时间，我把心目中的 “狗熊月读” 会员平台的构架梳理完毕。和小伙伴们讨论后，我们决定先最简化操作，制作一个包含了所有内容查看功能的小程序，跑完流程如果一切顺利，再加入会员登陆、注册购买等功能。事后发现，这是一个非常明智的决定。

![架构手绘](http://i.imgur.com/izt8rFZ.jpg)

小程序的开发需要服务器的相应配置，而作为腾讯系的产品，服务器选择腾讯云会比较好用，于是我购买了一个腾讯云的普通服务器，后端小伙伴 J 搭建好了服务器，并且根据我设计好的架构，写好了内容管理后台。小程序需要用域名解析，而且需要支持 https ，这些技术门槛都被一一搞定了。

然后 12 月底我女儿出生，那段时间我基本处于隐身状态，这个项目也暂停了近两周没怎么搞啦，辛苦了另外两位小伙伴。

2017 年 1 月 15 日，上传 1.0 小程序，被驳回，原因是：列表内的文字只能显示一半，显示不清晰。这时我发现小程序的审核团队对于细节的要求其实非常严格。部分字体不显示也无法通过。

![架构-kam](http://i.imgur.com/SLKJeLT.jpg)

2017 年 1 月 17 日，上传 1.1 版 “狗熊月读”，被驳回，原因是：服务类目 " 富媒体-资讯" 与你提交代码审核时设置的功能页面内容不一致:

> * (1):功能页面设置的部分标签不属于所选的服务类目范围。
> * (2):服务涉及类目包含富媒体—视频

我以为这是因为我们的小程序里包含了音频和视频，分类里选择的是资讯而不是视频的原因导致被拒，调节一下分类应该就行。但第二天调整后的结果仍然被驳回，原因是这样的：

>  * (1):功能页面所提供的内容不属于所选的服务类目范围。
>  * (2):服务属于富媒体-视频类目

我和伙伴们商议后，决定删掉视频功能（直接在代码里将其注释掉），再次提交了审核。19 日，结果出来了，再次被驳回，原来放音频也需要资质：

>  * (1):功能页面所提供的内容不属于所选的服务类目范围。
>  * (2):请补充提供富媒体-有声读物类目并提交资质文件。

查看了对于 “富媒体-有声读物” 类的资质要求后，我惊了：这几乎是地方级电视台或是电台才有可能通过的门槛。需要不少于 20 人的专职员工，以及注册资金不少于 500 万（好像是，我记不太清了，反正我们也没有）。最后，我将音频、视频功能全部砍掉的阉割版“狗熊月读”上传，2 月 21 日，这个人棍版“狗熊月读”通过了审核，上线了。但它对于我们来说，也算是正式失败了。用户通过这个小程序，完全不能为自己提供价值。

![Group](http://i.imgur.com/vpli740.jpg)

因此，我也完全没有在任何渠道提到过我们有开发过小程序，到目前为止，这个几乎只是纯展示的 “狗熊月读” 小程序，只有上百次用户打开，从数据上来看也算是失败了。

### 制作历程记录

> 1. 2016 年 11 月，注册了小程序开发者，并逐步完成了微信认证。
> 
> 2. 11 月 7 日，创建了小程序讨论 Slack 组，算是正式准备开始。
> 
> 3. 2016 年 12 月，讨论并确定了开发第一个版本的小程序试验 “狗熊月读” 小程序版，购买服务器（腾讯云）并进行设置。
> 
> 4. 确定了数据结构，开始搞后台
> 
> 5. 2017 年 1 月 15 日，上传 1.0 版“狗熊月读”小程序，被驳回。原因是：列表内的文字只能显示一半，显示不清晰。
> 
> 6. 2017 年 1 月 17 日，上传 1.1 版 “狗熊月读”，被驳回。原因是：服务涉及类目包含富媒体—视频
> 
> 7. 2017 年 1 月 18 日，上传 1.2 版 “狗熊月读”，被驳回。原因是包含视频的话必须提供影音资质证明。
> 
> 8. 2017 年 1 月 18 日，上传 1.3 版 “狗熊月读”，被驳回。原因是包含音频内容的话必须提供广播资质证明，这个比影音资质门槛更高。
> 
> 9. 2 月 21 日，人棍版的小程序 “狗熊月读”（去除了视频、音频，仅保留了一个查看 PDF 版读书笔记和思维导图的功能）通过了审核，但它已经没有意义了。
> 
> 10. 2 月 28 日，决定放弃 “狗熊月读” 小程序的开发，并对这个项目进行复盘。

## 失败原因分析
现在来看，我们这款小程序失败的原因，其实就是两个：

1. 将小程序当做了内容媒体提供渠道，定位错了；
2. 低估了微信对于小程序的谨慎态度。

### 定位错误
定位错误是最主要的问题。我们在开始确定第一个小程序的开发计划时，选择的是我的 “狗熊月读” 会员付费内容呈现。这是一个非常不符合小程序定位方向的开发目标。**小程序适合的类别，首先是一些线下服务的场景在线上的融合。** 比如共享单车，在拿到车时直接用微信小程序扫码，到站后结算走人，或是线下的传统服务业，使用小程序来增加用户的互动度。**第二种适合小程序的类别，是在线的小工具。** 比如算大姨妈周期，或是房贷车贷的计算器之类的工具。以提供内容为主的平台，其实已经有了很好的解决方案：微信公众号。微信没有必要，也不鼓励大家在小程序的平台上再做一次内容提供者。从小程序审核时对于音频、视频内容的资质要求如此严格，就可以看得出来。

### 微信对于小程序的谨慎
张小龙在演讲时，其实已经把小程序是什么讲得很清楚，但对于大多数开发者、关注者和热炒小程序的媒体来说，我们都不只想着做一个 “小” 的程序，而是想着不能错过下一个风口，特别是微信级别的风口。但从微信审核小程序的感觉来看，他们仍然延续着一直以来的谨慎态度，功能只是小步地放出，而审核上更是特别严格。这一点，我们低估了对于内容审核的严格。**作为多年的 iOS 开发者，我们习惯了 Apple 那种对于 UI、交互和设计内容的严格，却忽略了对于资质审核的要求。而这一点，是在国内做项目必须考虑的因素。** 我们失算了。

![](http://i.imgur.com/M55rBHP.jpg)

## 失败的收获
本身这次开发小程序的尝试就是一次试验，从试验的目的来说，我们达到了预定的目标，也算是成功了。初步梳理了一下，我们至少有下面的这些收获。

### 一次真实 Remote work 测试
这次开发小程序，我们一共有 3.5 个人进行。我作为产品架构设计及内容制作，身在新西兰的奥克兰；负责前端的 K 在昆明，后端及项目主程 J 在北京，协调处理微信认证的同事（事情不多，只能算 0.5 个人）身在昆明。我们是真正意义上的异地异步办公，但借助远程项目管理的 Slack和微信沟通，我们的工作流程处理得不错。这样的经验，以后的项目也可以用到。我一直想要成为真正的数字游民，这种 remote 式工作的方式越早开始越好。

### 知道了小程序是什么
这次试验开始前，我们都不知道到底小程序是什么，事实上我们直到做完了自己的小程序上传时，仍然没有搞清楚这东西到底是什么，但现在我知道了。**小程序是一个被连接的点，它可以被服务号连接，成为一种支持和完善服务的工具。最终，它也许会成为微信 “连接一切” 口号中一块不可缺少的部分。** 关于这一点，网络上聊的人很多，如果感兴趣，不妨也去读一读别人的文章。

![connet everything](http://i.imgur.com/AVt9BTk.jpg)

### 精益开发的经验
作为制作过 30 多个 iOS app 的老司机，我当然明白：**对于一个不确定性比较大的新领域，使用精益创业的思维来进行开发，是最好的选择。** 所以我虽然在最初进行产品架构时理出了包括微信支付在内的功能，但实际执行第一步时，我们都先用最小化的方式进行开发。另外，当发现项目其实并不是很有潜力且不是很值得继续下去时，我们果断地决定停止继续的工作。可以说我们这次尝试，也学会了一条经验：

> **"When you are involved in a wrong project, you can still make right desicion."**

## 其他
### 如何看待小程序？
小程序会是下一个风口么？目前来看不一定，可能会是，但一定不会是光炒作一下概念就可以把猪飞上天的风口。小程序已死么？别听那些连微信开发程序在哪里下载都不知道的自媒体忽悠，它还活得好好的呢。

**我觉得小程序的推出，是微信谨慎而充满野心的尝试。它的价值，在于最终的连接。**

> 说句题外话，其实与苹果乔布斯时代的黄金时期内核最相似的公司，在国内来看可能就是微信（注意不是腾讯）。微信支付相当于当年的 Apple ID 绑定了信用卡，微信小程序虽然目前还很低调，但引出了一个能够让第三方开发者加入的平台类似于当年的 iOS SDK 放出。类似于 Apple 的 iOS 系统，微信也是一个可以形成生态的平台，两者都有着数亿级的海量重度用户。最相似的是，两者都有着一个谨慎又有执行力的团队，和一个目光长远的领导者（张小龙 vs 乔布斯）。唯一的差别，就是微信不做硬件，苹果是跨越了硬、软件和操作系统的领域。但在一个基础互联网硬件（其实就是智能手机）差距已经越来越小的时代，跨越硬件领域真的有那么重要吗？

**现在对于小程序来说，最大的一个问题是用户没有合适打开它的逻辑关系。** 说简单一些，就是没有合适的场景需要用户打开微信的小程序去进行一个操作。正因为如此，我们的工程师小伙伴甚至认为没有二维码的场景就没有使用小程序的必要。但如果把小程序当做一个大的环节上解决问题的一个局部的话，可能这个问题就不是问题了。比方说一个公众号的文章是关于大姨妈的准时与否的科普文章，当你阅读到中途时，你可以点击文章里的按钮或扫码跳转到某个小程序，测试一下你的大姨妈周期是否准确。之后有了结果后再返回阅读，你可以直接阅读符合自己情况的部分。最后在服务号的链接里选择适合自己的推荐商品，直接通过微信支付完成购买。这才是使用小程序的全局化作用。**它的价值，在于帮助完成最终的连接。**

### 制作内容的人可以怎么办？
小程序绝对不是给内容制作者准备的。我的经历完全可以证明这一点。目前来说对于内容制作者来说，最适合的渠道还是微信订阅号或服务号。如果你打算构建自己的内容付费体系，那么也可以准备一个经过认证的微信服务号，并开通微信支付功能。在那之前，先努力地将自己的内容丰富起来，这要比去赶风口有价值得多。

