---
description: What is a DI / IoC?
---

# 💡 DI / IoC

## IoC

**inversion of control** (**IoC**) is a programming principle. IoC inverts the [flow of control](https://en.wikipedia.org/wiki/Control\_flow) as compared to traditional control flow. In IoC, custom-written portions of a [computer program](https://en.wikipedia.org/wiki/Computer\_program) receive the flow of control from a generic [framework](https://en.wikipedia.org/wiki/Software\_framework). A [software architecture](https://en.wikipedia.org/wiki/Software\_architecture) with this design inverts control as compared to traditional [procedural programming](https://en.wikipedia.org/wiki/Procedural\_programming): in traditional programming, the custom code that expresses the purpose of the program [calls](https://en.wikipedia.org/wiki/Function\_call#Main\_concepts) into reusable libraries to take care of generic tasks, but with inversion of control, it is the framework that calls into the custom, or task-specific, code.



&#x20;**dependency injection** is a [design pattern](https://en.wikipedia.org/wiki/Software\_design\_pattern) in which an [object](https://en.wikipedia.org/wiki/Object\_\(computer\_science\)) or [function](https://en.wikipedia.org/wiki/Subroutine) receives other objects or functions that it depends on. A form of [inversion of control](https://en.wikipedia.org/wiki/Inversion\_of\_control), dependency injection aims to [separate the concerns](https://en.wikipedia.org/wiki/Separation\_of\_concerns) of constructing objects and using them, leading to [loosely](https://en.wikipedia.org/wiki/Loose\_coupling) [coupled](https://en.wikipedia.org/wiki/Coupling\_\(computer\_programming\)) programs.[\[1\]](https://en.wikipedia.org/wiki/Dependency\_injection#cite\_note-1)[\[2\]](https://en.wikipedia.org/wiki/Dependency\_injection#cite\_note-MarkSeeman2011P4-2)[\[3\]](https://en.wikipedia.org/wiki/Dependency\_injection#cite\_note-3) The pattern ensures that an object or function which wants to use a given [service](https://en.wikipedia.org/wiki/Service\_\(systems\_architecture\)) should not have to know how to construct those services. Instead, the receiving '[client](https://en.wikipedia.org/wiki/Client\_\(computing\))' (object or function) is provided with its dependencies by external code (an 'injector'), which it is not aware of.[\[4\]](https://en.wikipedia.org/wiki/Dependency\_injection#cite\_note-HollywoodPrinciple.c2-4) Dependency injection helps by making implicit dependencies explicit and helps solve the following problems:[\[5\]](https://en.wikipedia.org/wiki/Dependency\_injection#cite\_note-5)

* How can a [class](https://en.wikipedia.org/wiki/Class\_\(computer\_programming\)) be independent from the creation of the objects it depends on?
* How can an application, and the objects it uses support different configurations?
* How can the behavior of a piece of code be changed without editing it directly?
