# 前言

在学校，我们学习计算机科学的方式与我们学习物理定律的方式相似。我们使用大O符号分析运行时间和空间复杂性，学习各种排序算法的工作原理，探讨不同的二叉树遍历方法。所以你可以想象，毕业后，我期望我的日常工作主要是科学性和数学性质的。但令我惊讶的是，实际情况并非如此。

事实证明，我需要做的大部分工作更多地涉及设计、结构和美学，而不是数学和算法。我从不需要考虑要使用哪种排序算法，因为通常会有一个库来处理这个问题（通常类似于`array.sort()`）。然而，我确实需要仔细思考我将创建的类，这些类上将存在哪些函数，以及每个函数将接受哪些参数。而这比我预期的要困难得多。

在现实世界中，我了解到完全优化的代码远不如良好设计的代码有价值。而这对于Web API来说尤为重要，因为它们通常有更广泛的受众和更多不同的用例。

但这引发了一个问题：什么是“良好设计”的软件？什么是“良好设计的Web API”？相当长一段时间，我不得不依赖于零散收集的资源来回答这些问题。对于某些主题，可能会有一些有趣的博客文章，探讨了当今一些常用的替代方案。对于其他主题，可能会有一些在Stack Overflow上特别有用的答案，可以指导我朝着正确的方向前进。然而，在许多情况下，关于所讨论主题的材料相对较少，我只能试图自己尝试给出答案，并希望同事们不会太讨厌它。

经过多年的这种经历（并携带着一个封面上写着“可怕的API问题”的笔记本），我最终决定是时候把我收集到的所有信息写下来，而且这些信息都是我亲身验证过的。一开始，这只是我和Luke Sneeringer为Google制定的一套规则，最终成为了AIP.dev。但这些规则有点像法律条文；它们告诉你应该怎么做，但没有解释为什么应该那样做。在经过大量研究和反复自问这个问题后，我写下这本书，不仅要呈现这些规则，还要解释为什么要这样做。

如果这本书是解决世界API设计问题的终极解决方案将会非常棒，但很不幸，我认为情况并非如此。原因很简单：就像建筑一样，任何类型的设计通常都是主观看法。这意味着有些人可能认为这些建议非常出色和优雅，会在今后的所有项目中使用它们。与此同时，也有一些人可能认为这本书呈现的设计是丑陋且过于限制性的，将其视为构建Web API时不应该采用的示例。因为我无法让每个人都满意，我唯一的目标就是提供一套经过实战验证的指南，以及为什么它们看起来这样的合乎逻辑的解释。

无论你是将它们用作跟随的示例还是要避免的示例，都由你决定。至少，我希望本书涵盖的主题引发尽量多的讨论，并激发人们未来更多探索API设计这个充满魅力和复杂的领域。