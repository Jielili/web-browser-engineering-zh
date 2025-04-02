# 前言 preface
A computer science degree traditionally includes courses in operating systems, compilers, and databases that replace mystery with code. These courses transform Linux, Postgres, and LLVM into improvements, additions, and optimizations of an understandable core architecture. The lesson transcends the specific system studied: all computer systems, no matter how big and seemingly complex, can be studied and understood.

一个计算机科学学位传统上包括操作系统，编译原理，数据库等课程，这些课程用代码揭开了神秘。它们让 Linux、Postgres 和 LLVM 不再是黑箱，而是可以改进、扩展和优化的可理解核心架构。这些课程教授的原理不仅适用于具体的系统（如 Linux、Postgres、LLVM），更重要的是，它们揭示了所有计算机系统的基本规律。因此，任何计算机系统，无论多么庞大或复杂，都可以被研究和理解。


But web browsers are still opaque, not just to students but to industry programmers and even to researchers. This book dissipates that mystery by systematically explaining all major components of a modern web browser.

但是网络浏览器仍然是一团迷雾，不管对学生还是对行业程序员，甚至对研究人员也是如此。本书通过系统地解释现代网络浏览器的所有主要组件，来消除这种神秘感。

## 阅读本书 Reading this book
Parts 1–3 of this book construct a basic browser weighing in at around 1000 lines of code, twice that after exercises. The average chapter takes 4–6 hours to read, implement, and debug for someone with a few years’ programming experience. Part 4 of this book covers advanced topics; those chapters are longer and have more code. The final browser weighs in at about 3000 lines.

这本书的1-3部分构建了一个基本浏览器，大约1000行代码。练习后的代码量大概是两倍。对于有几年编程经验的人来说，平均每章需要4-6个小时来阅读，实施和调试。这本书的第4部分涵盖了高级话题；这些章节更长，代码更多。最终的浏览器大约有3000行代码。


Your browser[1] will “work” at each step of the way, and every chapter will build upon the last.[2]This idea is from J. R. Wilcox, inspired in turn by S. Zdancewic’s course on compilers. That way, you will also practice growing and improving complex software. If you feel particularly interested in some component, please do flesh it out, complete the exercises, and add missing features. We’ve tried to arrange it so that this doesn’t make later chapters more difficult.

你的浏览器每一步都会“工作”。每一章都在上一章基础上构建。这个想法来自于 J. R. Wilcox，是受 S. Zdancewic 的编译器课程的启发。这样，你也可以练习如何扩展迭代和改进复杂的软件。如果你对某个组件特别感兴趣，请务必将其完善，完成练习，添加缺失的功能。我们希望这样的安排不会让后面的章节更难。


The code in this book uses Python 3, and we recommend you follow along in the same. When the book shows Python command lines, it calls the Python binary python3.[3] That said, the text avoids dependencies where possible and you can try to follow along in another language. Make sure your language has libraries for TLS connections (Python has one built in), graphics (the text uses Tk, Skia, and SDL), and JavaScript evaluation (the text uses DukPy).

这本书的代码用Python3编写，我们建议你也用Python3。当这本书展示Python代码行时，它调用的Python可执行文件是 python3.[3]。尽管如此，书中尽量避免依赖，所以你可以尝试用其他语言来实现。确保你的语言支持以下库：TLS链接（Python内置了一个），图形（书中使用TK，Skia和SDL），和JavaScript评估（书中内容使用DukPy）。


This book’s browser is irreverent toward standards: it handles only a sliver of the full HTML, CSS, and JavaScript languages, mishandles errors, and isn’t resilient to malicious inputs. It is also quite slow. Despite that, its architecture matches that of real browsers, providing insight into those 10 million line of code behemoths.

本书的浏览器不拘泥于标准：它只处理了HTML，CSS和JavaScript语言的一小部分，处理错误的方式不严谨，对恶意的输入也缺乏抵抗力。此外，它运行速度很慢。尽管如此，它的架构与真正的浏览器相匹配，能够帮助理解那些动辄上千万行代码的庞然大物。


That said, we’ve tried to explicitly note when the book’s browser simplifies or diverges from standards. If you’re not sure how your browser should behave in some edge case, fire up your favorite web browser and try it out.

尽管如此，我们尽量明确指出本书的浏览器在哪些地方进行了简化或者偏离了标准。如果你不确定你的浏览器在某些边界情况应该怎么运作，可以打开你最喜欢的网络浏览器试一试。


## 感谢 Acknowledgments
We’d like to recognize the countless people who built the web and the various web browsers. They are wonders of the modern world. Thank you! We learned a lot from the books and articles listed in this book’s bibliography—thank you to their authors. And we’re especially grateful to the many contributors to articles on Wikipedia (especially those on historic software, formats, and protocols). We are grateful for this amazing resource, one which in turn was made possible by the very thing this book is about.

我们要向无数构建网络和各种网络浏览器的人致敬。他们是现代世界的奇迹。感谢你们！我们从本书列出的参考书目和文章中学到了很多东西——感谢他们的作者。我们感谢维基百科上文章的贡献者们（尤其是那些关于历史软件，格式和协议的文章）。我们感谢这个了不起的资源，而它本身正是本书所探讨的技术所促成的。


Pavel: James R. Wilcox and I dreamed up this book during a late-night chat at ICFP 2018. Max Willsey proofread and helped sequence the chapters. Zach Tatlock encouraged me to develop the book into a course. And the students of CS 6968, CS 4962, and CS 4560 at the University of Utah found countless errors and suggested important simplifications. I am thankful to all of them. Most of all, I am thankful to my wife Sara, who supported my writing and gave me the strength to finish this many-year-long project.

Pavel：James R. Wilcox 和我在 2018 年 ICFP 的一次深夜交流中萌生了撰写本书的想法。Max Willsey 负责校对，并帮助安排章节顺序。Zach Tatlock 鼓励我将本书发展成一门课程。犹他大学 CS 6968、CS 4962 和 CS 4560 课程的学生发现了无数错误，并提出了重要的简化建议。我对他们所有人都心怀感激。最重要的是，我感谢我的妻子 Sara，她支持我的写作，并给予我完成这项多年项目的力量。


Chris: I am eternally grateful to my wife Sara for patiently listening to my endless musings about the web, and encouraging me to turn my idea for a browser book into reality. I am also grateful to Dan Gildea for providing feedback on my browser-book concept on multiple occasions. Finally, I’m grateful to Pavel for doing the hard work of getting this project off the ground and allowing me to join the adventure. (Turns out Pavel and I had the same idea!)

Chris：我永远感激我的妻子 Sara，她耐心地倾听我关于 Web 的无尽思考，并鼓励我将浏览器书籍的构想变为现实。我还要感谢 Dan Gildea 多次为我的浏览器书籍概念提供反馈。最后，我感谢 Pavel 做了艰苦的工作，帮助这个项目起步，并让我加入这场冒险。（结果证明，Pavel 和我有着相同的想法！）

## 最后一则说明 A final note

This book is, and will remain, a work in progress. Please leave comments and mark typos; the book has built-in feedback tools, which you can enable with Ctrl-E (or Cmd-E on a Mac). The full source code is also available on GitHub, though we prefer to receive comments through the built-in tools.

本书是一个不断进步的作品，并将继续保持这种状态。请留下评论并标记错别字；本书内置了反馈工具，您可以通过按 Ctrl-E（或 Mac 上的 Cmd-E）启用。完整的源代码也可以在 [GitHub](https://github.com/browserengineering/book) 上找到，尽管我们更倾向于通过内置工具接收评论。



[1]This book assumes that you will be building a web browser along the way while reading it. However, it does present nearly all the code—inlined into the book—for a working browser for every chapter. So most of the time, the book uses the term “our browser”, which refers to the conceptual browser we (you and us, the authors) have built so far. In cases where the book is referring specifically to the implementation you have built, the book says “your browser”.
本书假设你在阅读的过程中会一路构建一个网页浏览器。然而，它几乎在每一章中都呈现了完整的代码——直接嵌入在书中——用来实现一个可工作的浏览器。因此，大部分时候，书中使用'我们的浏览器'这个术语，指的是我们（你和我们，作者）到目前为止构建的概念性浏览器。在书中特别提到你所构建的实现时，则使用'你的浏览器'。

[2]This idea is from J. R. Wilcox, inspired in turn by S. Zdancewic’s course on compilers.
这个想法来自于 J. R. Wilcox，是受 S. Zdancewic 的编译器课程的启发。

[3]This is for clarity. On some operating systems, python means Python 3, but on others that means Python 2. Check which version you have!
这是为了清晰起见。在某些操作系统上，python 意味着 Python 3，但在其他操作系统上则意味着 Python 2。检查你拥有的版本！