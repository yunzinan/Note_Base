# 如何优雅地写slides?

!!! info "介绍"

    ​"都什么年代了, 还在用传统slides?!"

    ​自从笔者从大一下的寒假接触了markdown和typora后, 简直是开启了一个全新世界, 从那天起, 我就 **一次也没有** 再用过Microsoft Word作为文本创作工具了——从离开了word, 用上了markdown, 到后面又用上了latex, 货比三家, 领教了markdown的简练和latex的优雅, 再回看曾经使用的word, 就简直是惨不忍睹了. 当然, 对美的追求一旦开始, 就似乎一发不可收拾, 对于slides的制作, 也同样在思考, 除了Powerpoint之外, 有没有什么更优雅的创作方式?



首先, 根据我的需求, 首先来翻译翻译: 什么叫"优雅"?

从笔者的角度出发, 大概以下几点较为重要:

- [内容主导] 创作过程应该不过多花时间在排版上, 而不是像制作PPT一样, 每一页都要先`插入文本框`, 输入文字, `调整字体颜色粗细大小`, `调整位置`等. 这些非内容性的操作是傻瓜式的, 一方面容易上手, 但同时也使得编辑的交互模式十分冗余.
- [格式简洁] 编辑的时候不需要有太复杂的语法, 这样同样会增加不必要的精力开销. 一个极端的例子是使用HTML+CSS写slides, 这样可以做到极致地自定义化, 但同时复杂的语法同样也使得其不适合直接上手.
- [美观, 美观, 还是TMD美观] slides的作用是给观众看的, 当然要让观看者赏心悦目才行, 这是最重要的一点了. 过于plain的presentation同样是不好的.
- [*对公式/代码的支持*] 这一点对于理工科的童鞋来说几乎也是必备的需求了, 对于笔者来说, 如果不能正确美观地显示latex公式, 那么几乎是一票否决的.
- [*cool*] (这一点纯属装逼, 但是请原谅笔者的这种行为🤣.) 大家都看惯了PPT做slides, 如果突然出现一个"少数派", 我想会给大家带来一些新意(笔者在第一次看到jyy老师的slides时就感到大受震撼, 这也是笔者开始探索slides创作模式的动机).

如果你有与我相似的需求, 那么这篇文章应该对你有些帮助.

下面笔者就列举一些我的尝试. 并对每种模式按照上述的需求进行评价.

## 八仙过海, 各显神通---各种各样的slide创作模式

### jupyter notebook + reveal.md

!!! hint "这里有一个展示网站"

    [笔者在高级程序设计课程上做的第一个项目的项目介绍](https://ap-cap.vercel.app/)

- 实际上是给jupyter notebook安装一款将notebook格式的文件转换为reveal.js格式的HTML的插件. 具体可以查看笔者之前对jupyter notebook的介绍. 这使得slide的编写几乎是"附赠"的, 只需要在完成写作后, 将每个block转换为对应的功能页, 就可以轻松得到对应的slides. 这个workflow是相当顺畅的. 

- 内容基于markdown语法, 并且支持c/c++/python/R等语言, 同时也支持markdown内置html语法渲染功能, 兼容性基本够用.

- 个人认为缺点有不能自定义reveal.js的许多功能, 也不能自定义模板(也可能是我不会). 因此reveal.js强大的slide能力被较大地限制住了. 

### latex slides

大一上微积分的时候老师用的就是latex编写的slides, 非常适合用于撰写学术性的slides, 排版的能力也是相当优秀的, 也支持自定义模板, 因此从最终的效果来说是相当不错的, 尤其是在做学术报告上. 缺点就是比较费时, 写起来花的时间可能不比做PPT要少, 因此并不是一个日常的选择.

### reveal.js

- https://revealjs.com/
- 相当丝滑, 最大的特点就是加入了hjkl四向移动的思路, 这就很好的与文件树的形式匹配, 相比PPT的线性播放, 会有更好的层次感, 同时这个动画是相当优雅的. 
- 支持代码式地编辑和可视化编辑(付费), 而本地的代码式编辑需要几乎是掌握一门新的语言了, 学习成本较高, 同时内容丰富的代价就是编写的效率并不算高. 个人感觉比直接写HTML+CSS也好不到哪去. 而可视化的在线编辑器是很不错的, 缺点就是付费😥, 这几乎是小众的PPT的替代品了.
- 由于reveal.js不够便捷, 因此就有人开发了[reveal-md](https://github.com/webpro/reveal-md), 一款可以将markdown转换为reveal.js的工具, 非常不错. 但是似乎项目的维护不太好, 写起来也不是很方便. 笔者后面有空会研究一下这个工具.
- 这是一个比较不错的模板,[TonyCrane/slide-template: TonyCrane's slide template for reveal-md (github.com)](https://github.com/TonyCrane/slide-template)

### Marp[重点安利]

- marp是我最近才找到的一款md2slide的工具, 它有vscode的插件版本, 也有自己的CLI版本, 因此对完全不懂技术的小白也能友好食用.

- 基于markdown语法, 也可以开启对html语法的支持, 因此非常简洁, 同时没有过多的特定语法, 因此学习成本几乎为0. 

- 基于vscode, 即开即用, 没有多余动作, 也支持实施渲染. 

- 从slide的效果来看, 肯定是不如reveal.js的, 并且官方提供的默认模板实在是太丑了😅.

!!! success "小广告时间"

    于是, 笔者就自己动手写了一款个人认为简洁&美观的[template]([yunzinan/marp-theme-academic: Academic Presentation Slides with Marp (github.com)](https://github.com/yunzinan/marp-theme-academic)), 这个是[预览]([marp-theme-academic.vercel.app](https://marp-theme-academic.vercel.app/)). 如果觉得不错的话, 欢迎star & fork!:heart:

- 这也是目前笔者觉得较为不错的写slide的方式, 就像typora一样, 非常适合日常的slide编写. 比如项目的介绍, 就可以直接将readme.md转换为slide, 然后0成本部署在vercel上, 效果是看readme.md的一百倍有木有! 同时在日常写报告之类的, 也可以用这个来完成, 省去了将文稿转换排版的时间. 相当优雅! 
