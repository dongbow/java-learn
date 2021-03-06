## 观察者模式

### 定义
定义对象间的一种一对多的依赖关系。当一个对象的状态发生改变时，所有依赖于它的对象
都得到通知并自动更新。

### 场景
观察者 Observer（小明的女朋友、老妈）——【订阅】——>> 气象站 Subject（小明）

### 分类

#### 推模型
- 假定目标对象知道观察者需要的数据。

- 目标对象主动向观察者推送目标的详细信息，推送的信息通常是目标对象的全部或部分数据。

- 会使观察者难以复用。

#### 拉模型
- 假定目标对象不知道观察则具体需要什么数据。

- 目标对象在通知观察者的时候，只传递少量信息。

- 如果观察者需要更具体的信息，由观察者主动到目标对象中获取，相当于观察者从目标对象中拉数据。

- 一般这种模型的实现中，会把目标对象自身通过 update 方法传递给观察者。

### 优点
- 实现了观察者和目标之间的抽象耦合
- 实现了动态联动
- 支持广播通信

### 缺点
可能会引起无谓的操作，所有观察者都会进行 update 操作

### 使用场景
- 一个对象（观察者）的操作依赖于另一个对象（目标）的状态变化
- 更改一个对象（目标）时，同时需要连带改变其他对象（观察者），而且不知道究竟有多少个对象需要被连带改变
- 一个对象（目标）必须通知其他对象（观察者）