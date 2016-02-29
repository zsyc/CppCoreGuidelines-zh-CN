# <a name="main"></a>C++ 核心指南

2016/2/15

编辑：

* [Bjarne Stroustrup](http://www.stroustrup.com)
* [Herb Sutter](http://herbsutter.com/)

翻译：

* 李一楠 (li_yinan AT 163 DOT com)

本文档是早期草稿。本文档有错漏，格式也不正规。
本文档作为开源项目，发布版本为 0.6。
复制，使用，修改，以及创建本项目的衍生物，受到一份 MIT 风格的版权授权。
向本项目作出贡献需要同意一份贡献者授权。详情参见附属的 [LICENSE](LICENSE) 文件。
我们将本项目开放给“友好用户”进行使用，复制，修改，以及生产衍生物，并希望能够获得建设性的资源投入。

十分欢迎大家提出意见和改进建议。
随着我们的知识增长，随着语言和可用的程序库的改进，我们计划对这份文档不断进行修改和扩充。
当提出您的意见时，请关注[导言](#S-introduction)部分，其中概述了我们的目标和所采用的一般方法。
贡献者的列表请参见[这里](#SS-ack)。

已知问题：

* 仍未对规则集合的完整性、一致性和可强制实施性加以检查。
* 三问号 (???) 用于标记已知的信息缺失。
* 需要更新参考部分；许多前 C++11 的源代码都过于老旧。
* [To-do: 未分类的规则原型](#S-unclassified) 是一份基本上保持最新状态的 to-do 列表。

您可以[阅读本指南的范围和结构的说明](#S-abstract)，或者直接跳转到：

* [In: 导言](#S-introduction)
* [P: 指导思想](#S-philosophy)
* [I: 接口](#S-interfaces)
* [F: 函数](#S-functions)
* [C: 类和类层次](#S-class)
* [Enum: 枚举](#S-enum)
* [R: 资源管理](#S-resource)
* [ES: 表达式和语句](#S-expr)
* [E: 错误处理](#S-errors)
* [Con: 常量和不可变性](#S-const)
* [T: 模板和泛型编程](#S-templates)
* [CP: 并发](#S-concurrency)
* [SL: 标准库](#S-stdlib)
* [SF: 源文件](#S-source)
* [CPL: C 风格的编程](#S-cpl)
* [PRO: 剖面配置](#S-profile)
* [GSL: 指南支持库](#S-gsl)
* [FAQ: 常见问题的解答](#S-faq)

配套章节：

* [NL: 命名和代码布局](#S-naming)
* [PER: 性能](#S-performance)
* [N: 伪规则和错误的看法](#S-not)
* [RF: 参考](#S-references)
* [附录 A: 程序库](#S-libraries)
* [附录 B: 代码的现代化](#S-modernizing)
* [附录 C: 相关讨论](#S-discussion)
* [词汇表](#S-glossary)
* [To-do: 未分类的规则原型](#S-unclassified)

也可以查看具体的语言特性

* [赋值](#S-???)
* [`class`](#S-class)
* [构造函数](#SS-ctor)
* [派生 `class`](#SS-hier)
* [析构函数](#SS-dtor)
* [异常](#S-errors)
* [`for`](#S-???)
* [`inline`](#S-class)
* [初始化](#S-???)
* [lambda 表达式](#SS-lambdas)
* [运算符](#S-???)
* [`public`, `private`, 和 `protected`](#S-???)
* [`static_assert`](#S-???)
* [`struct`](#S-class)
* [`template`](#S-???)
* [`unsigned`](#S-???)
* [`virtual`](#SS-hier)

还有一些用于表达和讨论的术语的定义，它们不属于语言技术，而是有关设计和编程技术的术语。

* 错误（Error）
* 异常（Exception）
* 故障（Failure）
* 不变式（Invariant）
* 泄漏（Leak）
* 前条件（Precondition）
* 后条件（Postcondition）
* 资源（Resource）
* 异常保证（Exception Guarantee）

