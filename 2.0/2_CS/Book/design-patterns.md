# Design Patterns: Elements of Reusable Object-Oriented Software

by Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides

*I, [Michael Parker](http://omgitsmgp.com/), own this book and took these notes to further my own learning. If you enjoy these notes, please [purchase the book](http://www.amazon.com/Design-Patterns-Elements-Reusable-Object-Oriented/dp/0201633612)!*


## 设计原则

* 找出应用中可能需要变换之处，把它们独立出来，不要和那些不需要变换的代码混在一起。
* 针对接口编程，而不是针对实现编程
* 多用组合，少用继承
* 为了交互对象之间的松耦合设计而努力，将对象间的互相依赖降到最低
* 类应该对扩展开放，对修改关闭
* 要依赖抽象，不要依赖具体类
* 最少知识原则：只和你的密友谈话
* 好莱坞原则：别调用（打电话给）我们，我们会调用（打电话给）你
* 一个类应该只有一个引起变化的原因

## 设计模式

* 策略模式：定义了算法族，分别封装起来，让它们之间可以互相替换，此模式让算法的变换独立于使用算法的客户
* 观察者(Observer)模式：定义了对象之间的一对多依赖，这样一来，当一个对象改变状态时，它的所有依赖者都会收到通知并自动更新
* 装饰者(Decorator)模式：动态地将责任附加到对象上。若要扩展功能，装饰者提供了比继承更有弹性的替代方案。
* 工厂(Factory)模式：定义了一个创建对象的接口，但由子类决定要实例化的类是哪一个。工厂方法让类把实例化推迟到子类。
* 单件(Singleton)模式：确保一个类只有一个实例，并提供一个全局访问点。
* 命令模式：将“请求”封装成对象，以便使用不同的请求、队列或者日志来参数化其他对象。命令模式也支持可撤销的操作。
* 适配器模式：将一个类的接口，转换成客户期望的另一个接口。适配器让原本接口不兼容的类可以合作无间。
* 外观模式：提供了一个统一的接口，用来访问子系统中的一群接口。外观定义了一个高层接口，让子系统更容易使用。
* 模板方法模式：在一个方法中定义一个算法的骨架，而将一些步骤延迟到子类中。模板方法使得子类可以在不改变算法结构的情况下，重新定义算法中的某些步骤。
* 迭代器模式：提供一种方法顺序访问一个聚合对象中的各个元素，而又不暴露其内部的表示。
* 组合模式：允许你将对象组合成树形结构来表现“整体/部分”层次结构。组合能让客户以一致的方式处理个别对象以及对象组合。
* 状态模式：允许对象在内部状态改变时改变它的行为，对象看起来好像修改了它的类。
* 代理模式：为另一个对象提供一个替身或占位符以控制对这个对象的访问
* 复合模式：结合两个或以上的模式，组成一个解决方案，解决一再发生的一般性问题。
* 模式：在某情境context下，针对某问题的某种解决方案

## 要点

* 模式不是代码，而是针对设计问题的通用解决方案。
* 大多数的模式和原则，都着眼于软件变化的主题。
* 大多数的模式都允许系统局部改变独立于其他部分。
* 有多个观察者时，不可以依赖特定的通知次序。
* 装饰者模式意味着一群装饰者类，这些类用来包装具体组件。
* 装饰者类反映出被装饰的组件类型（事实上，他们具有相同的类型，都经过接口或继承实现）。
* 装饰者可以在被装饰者的行为前面与/或后面加上自己的行为，甚至整个取代掉。
* 装饰者会导致设计中出现许多小对象，如果过度使用，会让程序变得很复杂。
* 所有的工厂都是用来封装对象的创建。
* 工厂方法使用继承：把对象的创建委托给子类，子类实现工厂方法来创建对象。
* 所有工厂模式都通过减少应用程序和具体类之间的依赖促进松耦合。
* 依赖倒置原则，知道我们避免依赖具体类型，而要尽量依赖抽象。
* 命令模式将发出请求的对象和执行请求的对象解耦。
* 在被解耦的两者之间是通过命令对象进行沟通的。命令对象封装了接受者和一个或一组动作。
* 命令也可以用来实现日志和事务系统。
* 当需要使用一个现有的类而其接口并不符合你的需要时，就使用适配器。
* 当需要简化并统一一个很大的接口或者一群复杂的接口时，使用外观。
* 适配器模式有两种形式：对象适配器和类适配器。类适配器需要用到多重继承。
* 模板方法的抽象类可以定义具体方法、抽象方法和钩子。
* 抽象方法由子类实现。
* 钩子是一种方法，它在抽象类中不做事，或者只做默认的事情，子类可以选择要不要去覆盖它。
* 为了防止子类改变模板方法中的算法，可以将模板方法声明为final。
* 策略模式和模板方法模式都封装算法，一个用组合，一个用继承。
* 工厂方法是模板方法的一种特殊版本。
* 状态模式允许一个对象基于内部状态而拥有不同的行为
* 和程序状态机PSM不同，状态模式用类代表状态
* Context对象会将行为委托给当前状态对象。
* 通过将每个状态封装进一个类，我们把以后需要做的任何改变局部化了。
* 使用状态模式通常会导致设计中类的数目大量增加。
* 远程代理管理客户和远程对象之间的交互。
* 虚拟代理控制访问实例化开销大的对象。
* 保护代理基于调用者控制对象方法的访问。
* 代理模式有许多变体，例如：缓存代理、同步代理、防火墙代理和写入时复制代理。
* 代理在结构上类似装饰者，但是目的不同。
* 装饰者模式为对象加上行为，而代理则是控制访问。
* 和其他的包装者(wrapper)一样，代理会造成你的设计中类的数目增加。
* MVC是复合模式，结合了观察者模式、策略模式和组合模式。
* 模型使用观察者模式，以便观察者更新，同时保持两者之间解耦。
* 控制器是视图的策略，视图可以使用不同的控制器实现，得到不同的行为。
* 视图使用组合模式实现用户界面，用户界面通常组合了嵌套的组件。
* Model 2是MVC在Web上的应用
* 让设计模式自然而然地出现在你的设计中，不是为了使用而使用。
* 设计模式并非僵化的教条；你可以根据自己的需要采用或调整。
* 总是使用满足需要的最简单解决方案，不用它用不用模式。
* 学习设计模式的类目，可以帮助你自己熟悉这些模式以及它们之间的关系。

### Chapter 1: Introduction

* Expert designers know not to solve every problem from first principles, but reuse good solutions. This experience makes them experts.
* A design pattern names, abstracts, and identifies the key aspects of a common design structure that make it useful for creating a reusable object-oriented design.
* The hard part of object-oriented design is decomposing a system into objects, which is difficult because encapsulation, granularity, dependency, flexibility, performance, evolution, reusability, and more come into play.
* When designing, strict modeling of the real world leads to a system that reflects today's realities not but not necessarily tomorrow's. Abstractions are key to making a design flexible.
* Dynamic binding means that invoking a method doesn't commit to a particular implementation until runtime.
* An object's class refers to how it's implemented, while an object's type refers to only its interface.
* Class inheritance is a mechanism for code reuse and representation sharing, while interface inheritance describes when an object can be used in place of another.
* Inheritance's ability to define families of objects with identical interfaces is important because polymorphism depends on it.
* By manipulating objects through the interface of their abstract class, clients remain unaware of the specific types of objects they use, and the classes that implement them. This reduces implementation dependencies.
* Class inheritance is white-box reuse, because parent class internals are visible, while object composition is black-box reuse, because no internal details are visible.
* Class inheritance is directly supported by the programming language, and makes it easy to modify the implementation being reused.
* But class inheritance is fixed at compile-time, and breaks encapsulation, where the subclass becomes strongly coupled to the parent class. The parent class can change and become unsuitable for extension.
* Composition, unlike inheritance, doesn't break encapsulation, and there are fewer implementation dependencies. Also, it helps you keep each class encapsulated and focused on one task.
* Advantage of delegation is that you can compose behaviors at runtime, and change the way they're composed. It's an extreme example of object composition.
* Disadvantages of delegation are that dynamic nature can be hard to understand, and there can be runtime inefficiencies. Only use it when it simplifies, not complicates.
* A design that doesn't take change into account risks major redesign in the future. Unanticipated changes are invariably expensive.

