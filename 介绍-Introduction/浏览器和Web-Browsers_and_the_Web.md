# 浏览器和Web Browsers and the Web

I—this is Chris speaking—have known the web for all of my adult life. The web for me is something of a technological companion, and I’ve never been far from it in my studies or my work. Perhaps it’s been the same for you. And using the web means using a browser. I hope, as you read this book, that you fall in love with web browsers, just like I did.

我-这是Chris说的-在我成年生活中就一直与Web打交道。对我来说，Web某种技术伴侣，在我的学习和工作中从未远离过它。也许你也是这样。使用Web意味着使用浏览器。我希望，当你阅读这本书时，你会像我一样爱上网络浏览器。


## 浏览器和我

Since I first encountered the web and its predecessors,[2] in the early 1990s, I’ve been fascinated by browsers and the concept of networked user interfaces. When i surfed the web, even in its earliest form. I felt I was seeing the future of computing. In some ways, the web and I grew together-for exaample, 1994, the year the web went commerical, was the same year I started College; while there I spent a fair amount of time surfing the web, and By the time I graduated in 1999, the browser had fueled the famous dot-com sepculation gold rush. Not only that, but the company for which I now work, Google, is a child of the web and was founded during that time.

自从在20世纪90年代初，我第一次邂逅Web及其前身以来，我一直对浏览器和网络化用户界面这一概念概念着迷。当我上网冲浪时，即使是在Web的最初形式下，也感觉自己看到了计算机的未来。在某种程度上，我和Web算是一块长大的——例如，1994年，Web商业化的那一年，也是我开始上大学的那一年；在大学期间，我花了相当多的时间上网冲浪，而到我1999年毕业时，浏览器已经推动了著名的互联网泡沫投机热潮。不近如此，我现在工作的公司-Google也是Web的产物，成立于那个时期。

In my freshman year at college, I attended a presentation by a RedHat salesman. The presentation was of course aimed at selling RedHat Linux, probably calling it the “operating system of the future” and speculating about the “year of the Linux desktop”. But when asked about challenges RedHat faced, the salesman mentioned not Linux but the web: he said that someone “needs to make a good browser for Linux”.[3] Even back then, in the first years of the web, the browser was already a necessary component of every computer. He even threw out a challenge: “How hard could it be to build a better browser?” Indeed, how hard could it be? What makes it so hard? That question stuck with me for a long time.[4]

在我大一的时候，我参加了一个RedHat销售员的演讲。这个额演讲当然是为了售卖RedHat Linux，可能称其为“未来的操作系统”，并预测“Linux桌面年”的到来。但是当被问到RedHat面临的挑战时，销售员提到的确不是Linux，而是Web：他说需要一个人”为Linux制作一个好的浏览器“。即使在Web早起阶段，浏览器已经是每台计算机的的必要组件。他甚至掏出一个挑战：”制作一个更好的浏览器有多难？“ 确实，这该有多难呢？是什么让它如此困难？这个问题让我思考了很久。

How hard indeed! After eleven years in the trenches working on Chrome, I now know the answer to his question: building a browser is both easy and incredibly hard, both intentional and accidental. And everywhere you look, you see the evolution and history of the web wrapped up in one codebase. It’s fun and endlessly interesting.

确实有多难！在Chrome团队奋战了十一年后，我终于找到了这个问题的答案：构建浏览器既简单又极其困难，既是有意为之，又充满了意外。放眼望去，都会在一个代码库中看到Web的演变与历史。这既有趣，又让人着迷。

So that’s how I fell in love with web browsers. Now let me tell you why you will, too.

这就是我为什么爱上网络浏览器。现在让我告诉你为什么你也会。

## 历史中的Web

The web is a grand, crazy experiment. It’s natural, nowadays, to watch videos, read news, and connect with friends on the web. That can make the web seem simple and obvious, finished, already built. But the web is neither simple nor obvious (and is certainly not finished). It is the result of experiments and research, reaching back to nearly the beginning of computing, about how to help people connect and learn from each other.

Web是一个宏大而疯狂的实验。现在在Web上看视频，阅读新闻，和朋友交流看起来都是理所当然的事情。这可以让web看起来似乎是简单的，显而易见的，已经完备的。但是Web并不简单，也非显而易见（当然更没有完成）。它是无数实验和研究的成果，其历史几乎可以追溯到计算机发展的早期，这些实验和研究是为了帮助人们互相联系和学习。

In the early days, the internet was a world-wide network of computers, largely at universities, labs, and major corporations, linked by physical cables and communicating over application-specific protocols. The (very) early web mostly built on this foundation. Web pages were files in a specific format stored on specific computers. The addresses for web pages named the computer and the file, and early servers did little besides read files from a disk. The logical structure of the web mirrored its physical structure.

在早期，互联网是一个全球范围的计算机网络，主要连接着大学、实验室和大型企业的计算。浙西计算机通过物理电缆连接起来，基于特定应用协议通信。最早的Web正式构建在这个基础之上的。网页（web pages）是一种存储在特定计算机上的特定格式的文件。网页的地址直接包含了计算机的名称和文件路径，并且最初的服务器除了从磁盘读取文件外，几乎不做任何其他事情。换句话说，Web的逻辑结构映射他的物理结构。


A lot has changed. The HyperText Markup Language (HTML) for web pages is now usually dynamically assembled on the fly and sent on demand to your browser. The pieces being assembled are themselves filled with dynamic content—news, inbox contents, and advertisements adjusted to your particular tastes. Even the addresses no longer identify a specific computer—content distribution networks route requests to any of thousands of computers all around the world. At a higher level, most web pages are served not from someone’s home computer but from a major corporation’s social media platform or cloud computing service.


如今，Web已经发生了巨大的变化。网页的超文本标记语言（HTML）现在通常是动态实时生成的，然后按需发送到你的浏览器。被集成在一起的碎片是动态的内容——新闻，收件箱的右键，还有符合你兴趣的广告。甚至地址都不再指向某台的特定的计算机——内容分发网络（CDN）会将请求路由到世界范围内成千上万的任意一台服务器。在更高层面，大部分网页的内容已不再来自个人家庭计算机，而是托管在大兴公司社交媒体平替或者云计算服务上。


With all that’s changed, some things have stayed the same, the core building blocks that are the essence of the web:

尽管 Web 发生了诸多变化，但有些核心元素始终未变，它们构成了 Web 的本质：

- The web is a network of information linked by hyperlinks
- The user uses a user agent, called a browser, to navigate the web.
- Information is requested with the HyperText Transfer Protocol (HTTP) and structured with the HTML document format.
- Documents are identified by Uniform Resource Locators (URLs), not by their content, and may be dynamically generated.
- Web pages can link to auxiliary assets in different formats, including images, videos, Cascading Style Sheets (CSS), and JavaScript.
- All these building blocks are open, standardized, and free to use or reuse.
  
- Web 是一个由超链接连接的信息网络。
- 用户用浏览器作为用户代理来到行Web
- 通过超文本传输协议（HTTP）请求信息，以HTML格式呈现。
- 文档由统一资源定位符（URL）标识，而不是由其内容标识，并且可能是动态生成的。
- 网页可以链接不同格式的辅助资源，包括图像，视频，CSS样式表和JavaScript脚本。
- 所有这些人和热心元素，都是公开的，标准化的，免费使用的。


As a philosophical matter, perhaps one or another of these principles is secondary. One could try to distinguish between the networking and rendering aspects of the web. One could abstract linking and networking from the particular choice of protocol and data format. One could ask whether the browser is necessary in theory, or argue that HTTP, URLs, and hyperlinking are the only truly essential parts of the web.

从哲学角度来看，这些原则中或许有些是次要的。有人可能会尝试区分 Web 的网络通信与渲染部分，或者将超链接和网络通信从具体的协议和数据格式中抽象出来。也有人可能会探讨浏览器在理论上的必要性，或者认为 HTTP、URL 和超链接才是 Web 唯一真正不可或缺的核心要素。

Perhaps. The web is, after all, an experiment; the core technologies evolve and grow. But the web is not an accident; its original design reflects truths not just about computing, but about how human beings can connect and interact. The web not only survived but thrived during the virtualization of hosting and content, specifically due to the elegance and effectiveness of this original design.

或许如此。毕竟，Web 本质上是一场实验，其核心技术也在不断演进发展。然而，Web 并非偶然产物，它的最初设计不仅体现了计算机领域的规律，还反映了人类如何连接和互动的本质。正是因为这种最初设计的优雅与高效，Web 不仅在托管和内容的虚拟化过程中存活下来，反而更加繁荣。

The key thing to understand is that this grand experiment is not over. The essence of the web will stay, but by building web browsers you have the chance to shape its future.

关键的是这场宏大的实验还没有结束。Web 的本质将会表留，但是通过构建浏览器你有机会塑造它的未来。

## 真实的浏览器代码库






[1]Broadly defined, the web is the interlinked network (“web”) of web pages on the internet. If you’ve never made a web page, I recommend MDN’s Learn Web Development series, especially the Getting Started guide. This book will be easier to read if you’re familiar with the core technologies.
广义上定义，网络是互联网上相互链接的网页（‘网络’）。如果你从未制作过网页，我推荐MDN的学习网络开发系列，尤其是入门指南。如果你熟悉核心技术，这本书会更容易阅读。


