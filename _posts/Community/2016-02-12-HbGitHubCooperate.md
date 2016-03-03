---
layout: post
title: GitHub 协作五大业余姿势
description: 姿势业余虽不至酿成大错，但着实让人浑身不自在。本文复盘俺过往踩坑经历（其实就是被 @ZoomQuiet 大妈咆哮调教的血泪史）助你规避几大常见业余姿势，少走弯路，更快体会 GitHub 协作的舒爽乐趣。
category: community
---


近期看到不少同伴使用 GitHub 协作，我开始理解当初 [@ZoomQuiet 大妈](http://zoomquiet.io/) 和我协作时的痛苦感受----这不顺眼那不专业，比如用中文命名、创建 wiki 却不更新 sidebar、满屏 Issue 不及时 close、Issue 通篇没有一个超链接等，虽不至酿成大错，但实在让人浑身不自在。遂复盘自己踩坑经历（其实就是被大妈咆哮调教的血泪史 T_T）供你规避几大常见业余姿势，少走弯路，更快体会 GitHub 协作的舒爽乐趣。


注意：

- 若不了解 GitHub 是什么，请先移步 GitHub 基础教程：
	+ [GitHub 漫游指南 By Phodal Huang](http://github.phodal.com/)
	+ [Code School - Try Git](https://try.github.io/levels/1/challenges/1)
	+ [廖雪峰的 git 教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
	+ [Udacity 上的课程《How to Use Git and GitHub》](https://www.udacity.com/course/how-to-use-git-and-github--ud775)
- 本文所列建议主要针对非技术协作（即很少使用 `pull request` 协作）的知识管理型团队，如果你对所在团队是否是知识管理型团队无所谓，这篇文章不必往下看了;-)

![](http://openmindclub.qiniudn.com/ishanshan/blog/LogoGitHub1.jpg?imageView2/2/w/340)

嗯哼，如果你绕过以上两坎，那来看看我被咆哮嫌弃 N 次的业余姿势你中了几个吧……

## 用中文命名 wiki 或文件

>为什么?! 为什么?! 为什么?! 为什么?! 为什么?! 为什么?! 为什么?! 为什么?! 为什么?! 为什么?!
>
>要用中文名的文件呢?!?!?!??
>
>在 GitHub 世界或是其它任意计算机世界中,
>
>使用非 ASCII 字串为文件名,
>
>都象 在华尔街 高声显摆刚刚买咸菜占了两毛銭便宜!
>
>**恶俗到突破天际的行为!**

初次创建 wiki ，我以中文命名，被大妈在协作群里如是咆哮，记忆深刻。

由于更熟悉汉语，或不知道该以什么英文命名，不少人可能和我当初一样，会下意识地以中文命名文档。据观察，在 GitHub 中用中文命名 wiki Pages 或文件，是新手最常出现的姿势，尤其没有技术背景的新手。

那以中文名直接填写到 GitHub wiki（code 中也一样） title 中，有什么不妥？

- 对比一下由此生成的 wiki pages URL 就知道了
	- wiki title 为 「Test」 的页面：`https://github.com/ishanshan/example/wiki/Test`
	- wiki title 为 「测试」 的页面：`https://github.com/ishanshan/example/wiki/%E6%B5%8B%E8%AF%95`
	- 你觉得哪个 URL 更干净易懂简明专业？
  
- 再看一下目录，用中文真是不忍直视……
![](http://openmindclub.qiniudn.com/ishanshan/blog/HbGH006.jpg)
  
总之，为避免徒增烦恼，也避免被嫌弃，在 GitHub 命名中请别出现中文。

不仅在 GitHub 中，其它团队共同使用的文件命名，也都强烈建议使用非中文。毕竟中文同一个意思可以有多种表达，而各人用词、命名习惯不一样，难以形成共识，对于团队知识管理来说真是徒增其扰，举个例子：
![](http://openmindclub.qiniudn.com/ishanshan/blog/HbGH005.jpg)
<center>俺在某以中文为主的协作界面检索「品牌」后返回的结果</center>


检索「品牌」一词搜出来这么多，每次我都要点击不下6次，前后对比来确认哪个是最新的、可用的文档。若用 wiki 来管理文档，且用英文命名，就不必这么烦恼了，比如在集团仓库下：

  - BrandAnrenInfo
  - BrandOMCInfo
  - BrandOMCRule
  - BrandiBrainRule

每次直接在唯一指定文档上更新，同事也直接从唯一指定文档取用信息，岂不快哉？

当然，这需要建立在团队有统一的[文件命名规约](http://ishanshan.top/community/HbDocName.html)、同事也都熟悉并遵守的前提下。否则，别挣扎了，继续要找东西就在群里吼谁有/谁知道在哪儿吧……




## wiki pages 从不挂 sidebar 也不和 Issues 关联

>如果没有任何链接,这是个 孤悬文章, 惨烈地被人遗忘是必然的,,,,

看到我们在 GitHub 创建孤悬文档，大妈幽幽地表达无奈和嫌弃。

估计是使用网盘的惯性，很多创建 GitHub wiki pages 的小伙伴建完 page ，就没下文了，顶多发给共同协作的人，就再没然后。设想一下这样的习惯对团队知识管理和经验传承有什么影响？

- 是不是没有一个公共的页面知道目前团队里都有哪些资料/资源？
- 尤其当 wiki 中的文档越来越多却没有直观的索引时，团队成员是不是更不乐意整理和复用？
- 且更新 wiki，一般不会有自动提醒（包括邮件和关联的 slack 等信息集成服务），除非在个人消息中查看。但一般少有人从那里查看吧？消息实在太多……

所以，团队中具有良好的知识管理素养的成员，一般会使用类似 GitBook 的内在顺序在 wiki 中创建 page：

- 先在 Home/_sidebar.md 中设计一个合理的链接点
- 给出文档标题和 wiki 文件名
- 然后在合理的目录,创建 对应 文件名的 .md
- 再开始编辑 文件内容
- 并在提交前先 pull 仓库的变化,完成冲突解决后 push

完成以上动作后，通常会把驱动这个 wiki 完成的 Issue 追踪节点相互关联。
![](http://openmindclub.qiniudn.com/ishanshan/blog/HbGH001.jpg)
<center>除了放在 sidebar 中、和 Issue 关联，还和配套使用的文档关联以便取用</center> 

此外，还需在协作界面知晓相关人员，比如在微信群或任务看板中抛出链接（注意运用 GitHub 锚点特性）并艾特相关同事，通知对方查看并进行下一步行动:
![](http://openmindclub.qiniudn.com/ishanshan/blog/HbGH007.jpg)
<center>通知对方看某个 wiki</center> 

![](http://openmindclub.qiniudn.com/ishanshan/blog/HbGH012.jpg)
<center>通知对方看某个 Issue 的某个 comment</center> 

![](http://openmindclub.qiniudn.com/ishanshan/blog/HbGH013.png?imageView2/2/w/335)
<center>通知对方看自己修订了哪些内容</center> 

![](http://openmindclub.qiniudn.com/ishanshan/blog/HbGH014.png?imageView2/2/w/335)<center>通知对方看自己新增了哪些内容，内容不止一条时可用 commit 锚点快速定位所有新增内容</center> 


## 写文案真的只有「文案」

基于 git 的版本控制功能，wiki 非常适合进行文档管理，因为任何改动都能被记录并方便对比查看。如果你在私人目录建个文案自己看，这倒不碍事，自己记得创建了什么/用于什么场合/怎么命名，需要的时候可以及时找到就好。

但在团队仓库，你创建的东西，一般还需其他同事 知晓/修订/审核/使用。若此，你在某个公共目录创建了文案，没有注明这个文案上下文前后关联的任何信息，那

- 同事翻到这个文案，如何确定是否可用，可以用在何种场合？
- 确定不了是不是要来问你？
- 来问你是不是增加了沟通成本？……

知识管理型团队，一定要尽可能避免这类非必要沟通，节省所有人的时间呐。

所以，在公共目录创建文案时，良好的协作习惯是，在文案开头加上头部说明，以 `5W1H` 简要说明文案背景、使用情境（比如官网/微信/邮件/宣传册etc.）等信息，以便别的同事快速理解和使用。比如：
    ![](http://openmindclub.qiniudn.com/ishanshan/blog/HbGH015.jpg)

<center>标题比正文更重要，别漏了！</center> 

PS.更多创建文档的建议，可以参考这个 [协作文档撰写指南](https://github.com/OpenMindClub/Share/wiki/HbDoc) 。

## Issue 当 BBS 来用


由于 QQ、Wechat 等平台的 IM 特性，越来越多人习惯撕扯跳跃的碎片交谈；而 贴吧/BBS/V2EX 样的垒楼，更诱使参与者快速回复，而不是逐一回复观点；且也没人对某个话题负责，聊到哪儿算哪儿，任凭其是否有共识/结论，以及对于一头扎进来的人会有怎样的感受。

但在 GitHub 仓库进行的沟通一般是团队协作，协作是为推进事情不是闲扯，请转换成 `push-style`：

  - 对要讨论的内容，延续 [mailing-list 的礼仪](https://zh.opensuse.org/index.php?title=openSUSE:%E9%83%B5%E4%BB%B6%E5%88%97%E8%A1%A8%E7%B6%B2%E8%B7%AF%E7%A6%AE%E5%84%80&variant=zh-cn#.E4.BD.BF.E7.94.A8.E5.BA.95.E9.83.A8.E5.BC.B5.E8.B2.BC.E6.88.96.E4.BA.A4.E9.8C.AF.E6.A0.BC.E5.BC.8F.E4.BE.86.E5.9B.9E.E7.AD.94) ，采用 [inline reply](https://en.wikipedia.org/wiki/Posting_style#Interleaved_style) 或 [Bottom-posting](https://en.wikipedia.org/wiki/Posting_style#Bottom-posting) 的格式逐一回复观点，比如

  ![](http://openmindclub.qiniudn.com/ishanshan/blog/HbGH010.jpg)
  
  - 除了 assignee，其他人也自觉主动维护 Issue ，把已形成的共识及时更新到首个 comment 中，**以便其他打开这个 Issue 的同事可以快速知晓进展**
  - 若 Issue 完成，及时 close ，让人进入 Issues 主界面即可及时知晓目前正在进行的 Issue。为啥？谨记大妈督导：
  
>Issue 是过程讨论，尽量消灭 Issue 
>   
>长期复用的一切文案,要用 维基/仓库 收集
>
>Issue 永远只是暂时性任务的追踪/提醒/讨论!


    
当然，close Issue 不是点击 close 就完事儿的，请在 comment 中附上相关链接，以便继续追踪这个议题

 - 比如 Issue 成果的链接（通常是 wiki/code 等成品页面）
 - 比如由此引发的新 Issue 等
 - 或至少说明是 Happy ending 还是过期关闭还是啥，让同伴看到时不必问你就可以知道这个 Issue 进展如何。比如：


 ![](http://openmindclub.qiniudn.com/ishanshan/blog/HbGH003.jpg)
 <center>把共识更新在首个 comment ，close 前更新该 Issue 的进展或结果</center> 
 
多提一句，Issue close 后，若再需开启，还是可以 reopen 的，当然最好在 reopen 时说明原因，以便其他看到 Issue 的同伴迅速进入状态。

## 发 Issue 不加 labels/milestone/assignee


Issue 目前可以自行设置 `labels` `milestone` `assignee`，每一个设置其实都相当于一个搜索入口/分类维度。也就意味着，你可以至少按 3+1 个维度来划分你的 issue：

### labels

这是知识管理中最常见的分类方式，Issue 中已默认有一套 label 供君调用。还可根据各团队习性随意定制，方便快速查看某一类 Issues，比如：

- OM2Py 课程运营仓库中`StandUpMeeting` `Task`
- OM2Py 的学员仓库中`优秀学员示范` `C2T2` `公告` `Doc`（关闭了 wiki 模块，所以增设了 Doc 标签发布可长期使用的文档）

### milestone

若 miletone 设置合理，点开 miletone 界面，可一目了然当前项目进展如何（close 的 Issue 占比多少），比如：
![](http://openmindclub.qiniudn.com/ishanshan/blog/HbGH004.jpg)

由此反推 milestone 的设置思路：

- 一般按项目发展阶段的「时间节点」来设置 miletone，比如课程运营中的`课程设计` `招生` `入学` `正式教学` `复盘`等阶段
- 也可以设置没有时间节点的里程碑比如 `Chaos` 来承载没有明确截止时间的讨论 Issue
- 当然还可以有其他分类，欢迎根据自己项目的特点大胆尝试;-)
     
   
   
### assignee

在团队协作中，

>- Issue 永远只是暂时性任务的追踪/提醒/讨论!
- Issue 是过程讨论，尽量消灭 Issue !

若此，assignee 便是牵头推进此 Issue 至 close、消灭该 Issue 的直接负责人。设定 assignee 后，在 Issue 主界面便又多一个维度了解目前团队进展：

- 目前没有 close 的 Issue 都主要是谁在推进
- 也可根据 assignee 筛选查看，便可对某人负责的 issue 情况一目了然，比如有多少没 close，close 了哪些，结果如何。
  
---

明了这些，现在你应该能理解为啥团队协作发 Issue 若不设定 labels/milestone/assignee 这三项十恶不赦了吧？
  
什么都不设定，就相当于切断了这个 Issue 大部分搜索接口。 Issue 越积越多，团队更新换代后，虽有全文检索功能，但不知道有哪些关键词的新人，如何快速了解/获取自己想要的信息？难道又回到那个需要什么就在群里吼的局面？


这也是我越发难以容忍国内一些项目管理平台话题板块的原因：
 
 - 不可设标签
 - 不能分配给某人
 - 不能关闭

尤其处于一个高速发展却没全员形成良好的知识管理契约的团队，无论该变成文档的还是转换为任务的内容，都发在话题板块里，很快积攒几百条话题不说，更新异常迅速，使用的术语体系还不一样，导致搜索非常不便，难以快速了解目前进展、找到想要的内容。

嗷不吐槽了，总之 Issue 可供性强大，团队内形成默契的使用礼仪，用对 GitHub ，用对 Issue，幸福感会大幅提升的！

![](http://openmindclub.qiniudn.com/ishanshan/blog/LogoGitHub2.gif)
  

## 小结



唠叨了这么多改善大部分协作业余表现的建议，其实无非几个原则：

- 链接尽量简明干净，命名不使用非 ASCII 字串
- 尽可能增加页面间的连接，不生产孤悬页面
- Issue 尽量 close ，可复用资料放 wiki
- 发展过程可追溯，5W1H 助追踪


说得再简单些，转变一下思考角度就好：

>多从**团队知识管理**、**经验传承**的角度思考个人如何参与协作，而非自己一时便利想咋整咋整。

不过说着轻巧，做起来挺难的……协作三个月，俺依然不时被大妈精准吐槽无地自容 눈_눈

Anyway，欢迎看到这篇文章的你也和我分享实践经验，一起探索更多协作乐趣噻~



## CHANGELOG 

- 160212 完善配图 Blog 发布
- 160122 [在 WorkFlowy 起草](https://workflowy.com/s/ipYERU9UbH)

