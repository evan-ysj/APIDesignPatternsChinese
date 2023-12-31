# 关于本书

《API设计模式》是为了提供一组安全、灵活、可重用的构建Web API的模式而编写的。它首先涵盖了一些通用的设计原则，然后基于这些原则展示了一组设计模式，旨在为构建API时常见场景提供简单的解决方案。

## 关于本书的读者

《API设计模式》适用于任何正在构建或计划构建Web API的人，尤其是那些打算将API公开使用的人。熟悉一些序列化格式(例如JSON、Google Protocol Buffers或Apache Thrift)或常见的存储范式(例如关系数据库模式)当然很有帮助，但并非必需。如果您已经熟悉HTTP及其各种方法(例如GET和POST)，那将是一个额外的优势，因为在本书的示例中，HTTP是首选的传输方式。如果您在设计API时遇到问题并且在思考：“我相信一定有人已经解决了这个问题”，那么这本书就适合您。

## 本书的组织结构：一份路线图

这本书分为六个部分，前两个部分涵盖了API设计中的更一般性主题，接下来的四个部分专注于设计模式本身。第一部分开篇为本书的其余内容做了铺垫，提供了一些关于Web API以及将来将应用于这些Web API的设计模式的定义和评估框架。

- 第1章首先定义了我们所说的API以及API为什么重要。它还提供了一种框架，用于评估一个API的质量。
- 第2章扩展了第1章的内容，探讨了如何将设计模式应用于API，并解释了它们对于任何构建API的人都有用。它涵盖了API设计模式的基本结构，以及如何使用这些设计模式之一可以带来更好API的短期案例研究。

第2部分旨在进一步加强第1部分建立的基础，概述了在构建任何API时应考虑的一些通用设计原则。

- 第3章探讨了API中可能需要命名的各种组件以及在选择它们的名称时需要考虑的因素。本章还展示了尽管似乎是表面问题，但命名对于API设计至关重要。
- 第4章深入研究了较大的API，其中可能存在多个相互关联的资源。本章探讨了在确定资源及其关系时需要考虑的一系列问题，并涵盖了一些实例说明了需要注意规避的事项。
- 第5章探讨了API中应如何使用不同的数据类型以及这些数据类型的默认值。本章涵盖了最常见的数据类型，如字符串和数字，以及更复杂的可能性，如映射和列表。

第3部分从适用于几乎所有API的基本模式开始对设计模式进行详细介绍。

- 第6章仔细探讨了API的用户如何识别资源，深入研究了诸如墓碑标记(tombstoning)、字符集(character set)和编码(encodings)以及使用校验和(checksums)来区分缺失和无效ID等标识符的底层细节。
- 第7章详细概述了Web API的不同标准方法(get, list, create, update, delete)应如何工作。它还解释了为什么每个标准方法在所有资源上的行为方式都应该完全相同，而不是因应每个资源的独特特性而有所不同。
- 第8章扩展了两个特定的标准方法(get，update)，以解释用户如何与部分而不是整个资源进行交互。它解释了为什么这是必要且有用的(对用户和API都是如此)，以及如何在最小干扰的情况下保持对此功能的支持。
- 第9章进一步介绍自定义方法，为在API中实现任何类型的操作提供了可能。本章特别解释了何时使用自定义方法是有意义的(以及何时不是)，以及如何在自己的API中做出这一决策。
- 第10章探讨了一种独特的情景，即API方法可能不是瞬时(同步)的，以及如何为具有耗时操作——LROs(long-running operations)的用户方便地提供支持。它探讨了LROs的工作原理以及可以由LROs支持的所有方法，包括暂停、恢复和取消作业。
- 第11章涵盖了一种可重复执行作业的概念，有点像Web API的cron作业。它解释了如何使用执行资源(Execution resources)以及如何按计划或按需执行这些工作。

第4部分着重关注资源以及它们之间的关系，有点像对第4章的更广泛探讨。

- 第12章解释了如何将相关数据的小型、孤立部分隔离到单例子资源中。本章详细介绍了这种做法适用以及不适用的情况。
- 第13章概述了Web API中的资源应如何使用引用指针(reference pointer)或内联值(inline value)存储对其他资源的引用。本章还解释了如何处理特殊情况，例如随时间推移引用数据发生变化时的更新或级联删除。
- 第14章扩展了资源之间的一对一关系，并解释了如何使用关联资源(association resources)表示多对多关系。本章还涵盖了关于这些关系的元数据存储。
- 第15章探讨了在处理多对多关系时，使用添加和移除的快捷方法作为替代方案，而不依赖于关联资源。本章还涵盖了在使用这些方法时的一些权衡以及为什么它们可能不总是理想的选择。
- 第16章探讨了多态(polymorphism)的复杂概念，其中同名变量可以具有各种不同类型。本章涵盖了如何处理API资源上的多态字段，以及为什么应避免多态方法。

第5部分开始探讨面向整个资源集合的交互。

- 第17章解释了在API中如何复制或移动资源。本章解决了很多复杂的问题如处理外部数据、从不同的父级继承元数据以及应如何处理子资源。
- 第18章探讨了如何调整标准方法(get, create, update, delete)以在一个时间内操作多个资源的集合，而不是单个资源。本章还涵盖了一些棘手的问题，例如应如何返回结果以及如何处理部分失败。
- 第19章扩展了第17章中批量删除方法的概念以删除与特定过滤器(filter)匹配的资源。本章还探讨了如何解决一致性问题和避免数据意外破坏的最佳实践。
- 第20章仔细研究了非资源数据的注入。本章介绍了匿名写入(anonymous write)的使用和一致性问题，并探讨了在适用API时如何权衡此类匿名数据注入。
- 第21章解释了如何依赖于不透明的页面令牌(page tokens)，使用分页(pagination)来处理大型数据集的浏览。本章还演示了如何在单个大型资源内使用分页。
- 第22章讨论了如何处理应用筛选条件(filter criteria)以列出资源，并以最佳方式在API中表示这些筛选条件。这直接与第19章中讨论的主题相关。
- 第23章探讨了如何处理资源的导入(import)和导出(export)，以及相对于备份和还原操作的导入和导出操作的微妙差异。

第6部分关注API中相对不那么令人兴奋的安全(safety)和安全性(security)领域。这意味着确保API免受攻击者的威胁，同时还要确保API提供的方法不容易受到用户自己的错误行为的影响。

- 第24章探讨了版本控制的话题以及不同版本之间兼容性的含义。本章深入探讨了兼容性作为一个光谱的概念，以及在API中保持一致的兼容性政策定义的重要性。
- 第25章开始通过提供一种软删除(soft deletion)模式来保护用户免受其自身的威胁，允许资源从视图中删除而不完全从系统中删除。
- 第26章试图通过使用请求标识符(request identifiers)来保护系统免受重复操作的影响。本章探讨了使用请求ID的风险，以及一种确保在大规模系统中正确处理这些ID的算法。
- 第27章重点讨论允许用户在API中执行操作之前获得操作预览的验证性请求(validation requests)。本章还探讨了如何处理更复杂的问题，如实际请求和验证请求同时存在的副作用。
- 第28章引入了资源修订(resource revisions)的概念，作为跟踪变更的一种方式。本章还涵盖了一些基本操作例如还原到以前的修订，以及更复杂的话题例如如何将修订应用于层级结构中的子资源。
- 第29章提供了一种用于在API请求需要重试(retry)时通知用户的模式。本章还包括了关于不同的HTTP响应代码的准则，以及它们是否适合进行重试。
- 第30章探讨了如何验证单个请求以及在验证API用户时需要考虑的不同安全标准。本章提供了一个符合安全最佳实践的数字签名API请求规范，以确保API请求具有可验证的来源和完整性，且不会在未来被否认(repudiated)。

## 关于代码

本书包含许多源代码示例，既有带编号的代码块，也有与普通文本并排的代码。在这两种情况下，源代码都使用等宽字体进行格式化，以与普通文本区分开来。有时，代码也会用粗体显示，以突出显示与章节中之前步骤中的代码不同的代码，例如当新功能添加到现有代码行时。

在许多情况下，原始源代码已经重新格式化，我们添加了换行符并重新排列缩进，以适应书中可用的页面空间。即使这样还不够，代码块中还包括了行连续标记 (➥)。此外，在源代码中的注释通常在文本中描述代码时会被删除。许多代码块都附有代码注释，强调重要概念。

经过与初期读者和审阅团队的广泛讨论，我决定使用TypeScript作为标准语言。首先，对于那些熟悉动态语言（如JavaScript或Python）和静态语言（如Java或C++）的人来说，TypeScript很容易理解。此外，尽管它可能不是每个人的最爱，也不是所有读者都能立刻编写自己的TypeScript代码，但代码片段可以被视为伪代码，大多数软件开发人员应该能够理解其含义。

在使用TypeScript定义API时，有两个方面需要考虑：资源和方法。对于前者，TypeScript的原语（如接口）在定义API资源的模式(schemas)时有很强的表达力，使得API定义通常非常简短，几乎总是可以放在几行之内结束。因此，所有API资源都被定义为TypeScript接口，这还具有使JSON表示变得非常明显的额外优势。

对于API方法，问题会稍微复杂一些。在这种情况下，我选择使用TypeScript的抽象类来表示整体API本身，使用抽象函数来定义API方法，这是一种通常用于Google的Protocol Buffers的RPC的约定。这样能够仅定义API方法，而无需担心底层实现。

在考虑API方法的输入和输出时，我决定再次依靠Protocol Buffers，考虑使用请求(request)和响应(response)接口。这意味着在大多数情况下，会有表示这些输入和输出的接口，以API方法的名称为基础，附加 `-Request` 或 `-Response` 后缀（例如，`CreateChatRoomRequest` 用于 `CreateChatRoom` API 方法）。

最后，由于这本书在很大程度上依赖于RESTful概念，必须有一种将这些RPC映射到URL（以及HTTP方法）的方法。为此，我选择使用TypeScript装饰器作为各种API方法的注释，每个不同HTTP方法会有一个注释（例如，`@get`、`@post`、`@delete`）。为了指示API方法应映射到的URL路径，每个装饰器都接受一个持请求接口中变量通配符的模板字符串。例如，`@get("/{id=chatRooms/*}")` 会在请求中填充ID字段。在这种情况下，星号表示一个除了斜杠字符以外的任何值的占位符。

尽管使用OpenAPI规范来定义所有这些设计模式可能是很好的选择，但有一些问题可能对这本书的读者不太友好。首先，OpenAPI规范主要是供计算机（例如，代码生成器、文档渲染器等）使用的，因为这本书的目标是向其他API设计师传达复杂的API设计主题，所以OpenAPI似乎并不是最好的选择。

其次，无论是使用YAML还是JSON格式，OpenAPI都相当冗长。不幸的是，使用OpenAPI来表示这些复杂主题完全是可能的，但并不是最简洁的选择，会带来很多额外的内容，而未能添加太多价值。

最终，在OpenAPI、Protocol Buffers和TypeScript之间，初期读者和审阅者明确反馈，对于这种特定用例TypeScript是最佳选择。请记住，我并不主张人们使用TypeScript来定义他们的API。这只是这个项目的一个非常合适的选择。

## 线上论坛

购买《API设计模式》将包括免费访问由Manning出版社运营的私人网络论坛，您可以在论坛上对书籍提出评论、提问技术问题，并得到作者和其他用户的帮助。要访问论坛，请前往 https://livebook.manning.com/book/api-design-patterns/welcome/v-7 。您还可以了解更多关于Manning论坛以及行为规则的信息，链接是 https://livebook.manning.com/#!/discussion 。
Manning对我们的读者承诺提供一个有意义的平台，使个体读者之间以及读者与作者之间可以进行深入的对话。这并不意味着作者会有特定数量的参与承诺，作者对论坛的贡献仍然是自愿的（且未获报酬）。我们建议您尝试向作者提出一些具有挑战性的问题，以保持他的兴趣！只要这本书还在印刷中，论坛和以前的讨论存档将从出版商的网站上获得访问权限。

## 其他线上资源

要进一步阅读有关API设计相关的内容，请访问 https://aip.dev，该网站详细介绍了许多类似的主题。