---
title: "中文分析比特币最早的文章之一是我写的，七年后的今天我写了第二篇"
date: 2018-03-02T00:00:00-05:00
showDate: true
draft: false
tags: ["blog","tech", "crypto"]
---

写过上一篇[暗网的文章](../the_darknet/)之后，按照大家的预期，我顺理成章应该写到区块链了。实际上也是如此，在去年这一年里面，我几次写到了相关话题，比如[互联网中心化偏离了最早的预期](../the_old_internet_is_end/)，比如分布式系统上建立的暗网代表了一种自由，但是一直没有专门写一篇关于区块链的文章。区块链的话题很有意思，值得多写几篇，就把本文算作第一篇吧。

<!--more--> 

去年年底开始，区块链热潮席卷世界，几乎每个人都在谈论它。但很少有人真正说清楚它，我看很多人写的文章用各种奇怪的东西来描述它，用一些更复杂，人们更不熟悉的概念来描述一个相对简单的概念，那当然越说越糊涂。区块链是非常有意义的发明，但是它的本质是简单的。除了少数关于数学证明和纯技术的话题有一定复杂性，要理解它是什么，进而理解它如何影响社会，没有那么困难。所有其他试图把它讲的非常复杂的人，要么自己不懂，要么就是故意让别人看不懂。

中文世界里，除了翻译的新闻之外，第二篇认真分析比特币的文章，[是我写的](../bitcoin/)。写于 2011-05-23 ，在我[过去的blog上](http://blog.devep.net/virushuo/2011/05/23/bitcoin.html)仍然可以看到这篇文章。（第一篇是[云风写的](https://blog.codingnow.com/2011/05/bitcoin.html)）有意思的是，在我2011年这篇文章里面写到的话题，到今天还有很多人在争论。当然，2011年和今天人们对比特币的理解是不一样的，那个时代还是远古时期，我在文章里面写着“用我的MBP一周能挖到5个比特币”。那个时代人们还在思考如何让更多人接受它，使用它进行交易。比特币买Pizza也出现那个时候。当时Blogger之间互相赠送比特币，我还在当时的公司盛大创新院送了不少给同事，很多人甚至连装个钱包收下它都不肯。郎闲平那张“你给我比特币我是不会要的”的截图实际上是当时人们普遍心态，和今天的情况是完全不一样的。

这些年的变化非常有趣，人们对区块链世界的认识也变得完全不同。它不再是地下世界的玩具，而是真正开始影响了太多人的现实世界。是时候写一篇新的了。

今天我们看到了各种名词，区块链和什么结合，智能合约如何如何，各种业务如何发展，眼花缭乱，但如果说背后的道理，仍然非常简单。这些概念都不是突然冒出来的，而是有漫长的历史争执和妥协。看明白了这个过程，就明白了今天的一切。所以，我们不说复杂的技术名词，回到2009年，看看历史。

2009年，比特币成功建立起了一种不依赖中心认证的交易系统，并且创造了一种在局部被承认的货币。从2010年开始，人们就在讨论是不是可以在比特币的网络上，存储一些交易之外的数据。后来一些人决定仿照比特币建立一个独立的系统去做这件事。最终，这形成了比特币的第一个分叉，叫做Namecoin域名币。域名币没有多火，市值没有暴涨，不是活跃交易的币种，没上多少个交易所，但是它到今天仍然存在，生命力非常顽强，如果你订阅我公众号的zeronet版本，在那边可以使用我的域名 huoju.bit 这就是通过namecoin注册到的域名，普通DNS无法解析，只能用在几个P2P系统里面。

很长一段时间里，从比特币分出来的altcoin（山寨币）里面，这是唯一一个真正有实际应用场景的币，然而除了哪些已经消失的，所有存在的早期山寨币里面，这是最不值钱的一个。

继续说回比特币。从2010年开始，比特币社区长期存在的争议就是，比特币网络里面到底是否可以存普通数据。一派人认为坚决不可，比特币是交易网络，只应该保存交易数据，否则就是滥用，何况比特币的数据库本来就在日益膨胀，增加数据有害无利。另外一派人的看法是应该允许这种行为，这样会提供更多的可能性，也确实有实际需求。何况，就算你不允许，用户实际上也在利用比特币数据结构里面各种空隙，发明了千奇百怪的存数据的办法。既然已经发生了，还不如正视这个问题。

最终讨论的结果是，几方妥协，引入了一个字段叫做OP_RETURN，它有80个bytes长，非常小，而且按照团队的说法，它本意设计出来并不是存其他数据的，而是用来标记一笔交易无效的记录。但不管团队怎么说，80 bytes已经足以写入一些简单信息了。别小看这一点点夹缝中的信息，因为它在比特币网络上存在，不可更改或者消除，这已经可以用来实现很多功能了，比如在里面存一份合同的hash，然后在比特币网络之外存储这份合同全文，拿到合同的用户只需要自己计算合同的hash，然后再和之前存放在比特币网络上的hash做对比，就可以知道拿到的是不是原始那份合同。

这个时期后来被称作“染色币”时期，大约是2014年，染色的意思就是和上面这个例子类似，利用比特币网络上存着的这80 bytes的信息，关联到一个比特币网络之外的存储上，使得两者被链接起来，这就叫染色。比特币社区对OP_RETURN仍然存在争议，在被滥用和提供更多功能之间摇摆，最终核心开发组决定缩减OP_RETURN的存储空间到40bytes，使得能存储的数据变少。这种方式最大的问题还是过于繁琐，绕来绕去，对于普通人要理解这个过程都很麻烦，更别说去用它，所以始终没成过主流应用。

既然类似染色币的需求确实存在，比特币又不愿意支持它，那么为什么不搞一种专门支持这类应用的链呢？如果担心滥用存储浪费资源，那么仍然拿出经济杠杆，要花钱才能用，这不就解决了问题？最终，以太坊诞生了。既然能存储任意数据，那么能不能干脆把可执行的代码也存储进去？这样不就可以实现更多功能了嘛？以太坊就是这么做的，它实现了自己的图灵完备编程语言和虚拟机，把这种编程语言编译之后的二进制代码存在链上，并且计算代码里面每一条指令的开销，以此计费，这样就形成了一个完整的经济系统，用户可以花费代币购买存储空间和运算能力，结果也存储在链上。这些都是不可篡改，不能销毁的。这些代码就叫做智能合约，智能合约这个词并不是以太坊的发明，这个构想和这个词的使用，可以追溯到90年代。并且在染色币的时代，人们就在链外实现了类似的功能。按照历史推理，这些发展都是顺理成章的，但在现实世界中，这已经从2009年到了2015年，按照今天“币圈一日，互联网一年”的说法，这可是相当漫长的时期了。

以太坊的发展也并不怎么顺利，中间遭遇了被黑，分叉，DDos攻击…很多风险，但最终以太坊还是活了下来。以太币早期没有这么热，如果看价格历史，可以看到实际上是2017年下半年它才开始飞速涨起来的。在早期，甚至还有基于以太坊的图床应用，让人们付一点ETH就可以把一张图片存在以太坊的链上，今天看来简直丧心病狂。在2017年前半年，还有人做了一个应用，从各种名画上找露胸的部分截图存到以太坊链上，说用这种方式来提醒人们，区块链的不可篡改特性是双刃剑，如果有人把你不合适的东西放上去，你也永远没法消灭它。（见 https://boobies.surge.sh）

在那一段时期内，以太坊有一个重要的特性被低估了，就是它可以非常容易的发行自己的代币（token）。在用比特币代码分叉的山寨币年代，还需要一定的开发能力，一定的运算资源保证，才能发行出自己的币。在以太坊上，只需要100多行代码，随手就可以发布一个新币。这种特性直到ICO开始火爆起来，才进入普通人视野。而我们今天看到的一切激动的，混乱的，可怕的状况，都源于此。这时候，已经是2017年下半年了。

回头看这些年的历史，区块链改变了什么？它建立了一个以网络和算法构成的，无权威中心又不容易被操控的分布式系统。它的优点、缺点、局限，也都在这个特性中包含了。无论想进行区块链的投资，还是想实际参与项目，都应该弄清楚它的这些独特特性，这样才能在各种眼花缭乱的每天出现的新名词前面保持清醒，看明白背后的东西。

无论人们把区块链描述成什么，它仍然是一种分布式系统，仍然屈从于分布式系统的铁律CAP定理，在一致性，可用性和分区容忍性三者中只能同时满足两者。而我们知道区块链系统既然要分布，要防止恶意节点，就意味着已经确定了必须同时满足分区容忍性和一致性，那么一定牺牲可用性。翻译成人话就是：“它就是很慢。” 一些优化可以提高速度，但无论怎么提高，它仍然是一种很慢的系统。这使得很多简单叠加的业务模型不存在，也没有存在的必要，因为传统的数据库系统仍然是他们最好的选择。但另外一方面，在伪需求之外，这些特点也使得一些过去难以实现的需求可以被解决，因为之前难以被实现，所以它的业务模型很可能是我们过去完全没见过的。90年代，人们可以想象在网络上卖书，但难以想象社交网络和云计算，更难以想象有一天人们能掏出手机上网，随时使用微信聊天和支付。如何识别这些项目，如何辨别哪些项目是伪需求，这是每一个新时代来临时候的生存必备能力。

对于经过互联网前泡沫时期的人，今天的一切完全不陌生。今天不管什么业务都恨不得加上区块链三个字使之变得更有吸引力，在90年代对应的词叫做 鼠标+水泥（Clicks and Mortar），鼠标指互联网商业模式，水泥指传统商业模式。任何业务只要靠上了互联网，估值就会飞涨，那也是一个天才、疯子、伟人、骗子混在一起的年代。后来发生的事情大家都知道了，并不是所有商业模式都适合互联网，并不是挂上互联网三个字，就真的能成为互联网企业，并不是所有适合互联网的商业模式，在当时的基础设施条件下都可以实现。但伟大的企业google、amazon已经从车库里探出了脑袋。


这篇本来应该是在两个月之前写好的，但是实在太忙了，一直拖到了现在。如果你同时是《神秘的程序员们》漫画的读者，应该知道我忙的原因是什么，是的，我决定和笑来一起做Press.One。这本来是我们在比特币出现之前就讨论过的事情，但之前的条件难以实现，区块链发展到今天，它有了实现的基础。其实我们认识这些年里面，有很多次讨论过类似的想法，上一次讨论是2017年下半年，那时候我忙于别的事情，没法参与。后来出了一些大家都知道的事情，项目也暂停了。年初的时候，笑来问我，区块链技术现在已经大不一样了，愿意再来做点事吗？于是我就这样接下了重启的Press.One。到现在为止，它仍然非常早期，但是已经能看出来一点点有意思的东西了。我们完成了去中心、基于社交身份的身份验证，可以用自己的钱包文件（私钥）来签名一份文件，这些信息保存在区块链上之后，就可以轻松确认发布者是谁，什么时间发表。还记得本文开头的时候，我说我写了中文关于比特币分析的第二篇文章吗？如果不是我在上面放了一个比特币钱包地址接受打赏，而且确实当时就收到了打赏，恐怕今天我已经没办法证明那篇文章真的发表在2011年而不是后来伪造的。那个时候的比特币玩家都会在Blog上放上自己的地址，并且互相赞赏。顺着我的地址，能看到来自云风的赞赏以及我赞赏给庄表伟、笑来、朱峰的记录。这些记录组成了一个网络，没有一个权威机构证明我们在那时候研究过比特币，但是大家用这种方式互相证明了对方的存在，尽管这种证明和我当时写过那篇文章之间的联系仍然是比较弱的。有了Press.One之后，要证明这样的事情就容易多了。

并且，在[我的Profile页面](https://press.one/main/p/becd34540fefeab83730ffb479e98ee12fa1337e)上，可以看到我签名的所有文件，这些都是我打算公开让所有人看到的信息，所以只要你跟踪我的Profile，就知道我发布了哪些我觉得重要的事情，那些我没打算赖账又不怕公布的事情。简单的可能有在一个群里面证明我是我，复杂的比如这篇文章最初的发布版本和作者是谁…所有我认为值得签名存证、声明我拥有著作权的东西，最终都会出现在这里。

当然，这仍然只是一小步，有意思的事情还在后面。而且…发布入口还没完成，虽然我自己现在已经能以内测为名义签名这篇文章，你也能看到我的feeds了，但距离完全开放，还有一点点距离。

如果这篇文章里涉及技术的部分你觉得理解起来有困难，不要紧。《神秘的程序员们》漫画正在画一个区块链的科普系列，用漫画的形式每期回答一个人们真正关心的区块链相关的疑问。讲技术，但不限于技术。

你可以顺着这个签名去验证我的数字签名，看本文原始快照，以及到我的profile页面看看我还签名了什么。

ps，我的Profile页面的feeds，是json feeds格式，它可以被理解成新时代优化过的RSS，所以如果找到合适的订阅器，是可以订阅我的Feeds的。如果找不到，没关系，等Press.one的App吧。

区块链是个好话题，以后我还会再写的。如果你有问题，也可以留言告诉我，我将来一起写。

