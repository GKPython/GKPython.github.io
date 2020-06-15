---
title: The zen of go
date: 2020-04-19 14:33:43
tags: 技术
---
转自以下：
https://the-zen-of-go.netlify.app/
https://www.oschina.net/news/113606/the-zen-of-go
The Zen of Go

Ten engineering values for writing simple, readable, maintainable Go code. Presented at GopherCon Israel 2020.

**Each package fulfils a single purpose**
    A well designed Go package provides a single idea, a set of related behaviours. A good Go package starts by choosing a good name. Think of your package’s name as an elevator pitch to describe what it provides, using just one word.

**Handle errors explicitly**
    Robust programs are composed from pieces that handle the failure cases before they pat themselves on the back. The verbosity of if err != nil { return err } is outweighed by the value of deliberately handling each failure condition at the point at which they occur. Panic and recover are not exceptions, they aren’t intended to be used that way.

**Return early rather than nesting deeply**
    Every time you indent you add another precondition to the programmer’s stack consuming one of the 7 ±2 slots in their short term memory. Avoid control flow that requires deep indentation. Rather than nesting deeply, keep the success path to the left using guard clauses.

**Leave concurrency to the caller**
    Let the caller choose if they want to run your library or function asynchronously, don’t force it on them. If your library uses concurrency it should do so transparently.

**Before you launch a goroutine, know when it will stop**
    Goroutines own resources; locks, variables, memory, etc. The sure fire way to free those resources is to stop the owning goroutine.

**Avoid package level state**
    Seek to be explicit, reduce coupling, and spooky action at a distance by providing the dependencies a type needs as fields on that type rather than using package variables.

**Simplicity matters**
    Simplicity is not a synonym for unsophisticated. Simple doesn’t mean crude, it means readable and maintainable. When it is possible to choose, defer to the simpler solution.

**Write tests to lock in the behaviour of your package’s API**
    Test first or test later, if you shoot for 100% test coverage or are happy with less, regardless your package’s API is your contract with its users. Tests are the guarantees that those contracts are written in. Make sure you test for the behaviour that users can observe and rely on.

**If you think it’s slow, first prove it with a benchmark**
    So many crimes against maintainability are committed in the name of performance. Optimisation tears down abstractions, exposes internals, and couples tightly. If you’re choosing to shoulder that cost, ensure it is done for good reason.

**Moderation is a virtue**
    Use goroutines, channels, locks, interfaces, embedding, in moderation.
Maintainability counts


知名 Go 语言贡献者与布道师 Dave Cheney 发表了名为《The Zen of Go》
编写简单、可读、可维护的 Go 代码的十个工程要点。

**每个包实现单一目标**
设计良好的 Go 软件包提供一个单一的思路，以及一系列相关的行为。一个好的 Go 软件包首先需要选择一个好名字，使用电梯法则（30 秒内向客户讲清楚一个方案），仅用一个词来思考你的软件包要提供什么功能。

**明确处理错误**
健壮的程序其实是由处理故障案例的片段组成的，并且需要在故障出现之前处理好。冗余的if err != nil { return err }比出了故障再一个个去处理更有价值。panic 和 recover 也一样。

**尽早 return，不要深陷**
每次缩进时都会在程序员的堆栈中添加另一个先决条件，这会占用他们短期内存中的 7±2 个片段。避免需要深层缩进的控制流。与其深入嵌套，不如使用守卫子句将成功路径保持在左侧。

**并发权留给调用者**
让调用者选择是否要异步运行你的库或函数，不要强制他们使用异步。

**在启动 goroutine 之前，要知道它什么时候会停止**
goroutines 拥有资源、锁、变量与内存等，释放这些资源的可靠方法是停止 goroutine。

**避免包级别的状态**
要完成明确和减少耦合的操作，需要通过提供类型需要的依赖项作为该类型上的字段，而不是使用包变量。

**简单性很重要**
简单性不是老练的代名词。简单并不意味着粗糙，它意味着可读性和可维护性。如果可以选择，请遵循较简单的解决方案。

**编写测试以确认包 API 的行为**
软件包的 API 是与使用者的一份合约，不管先后，不管多少，一定要进行测试。测试是确定合约的保证。要确保测试使用者可以观察和依赖的行为。

**如果你认为速度缓慢，先通过基准测试进行验证**
以性能之名会犯下许多危害可维护性的罪行。优化会破坏抽象、暴露内部和紧密耦合。如果要付出这样的代价，请确保有充分理由这样做。

**节制是一种美德**
适度使用 goroutine、通道、锁、接口与嵌套。
