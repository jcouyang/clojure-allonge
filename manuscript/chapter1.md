# 第一章 我每天用括号当早饭<a id="sec-1" name="sec-1"></a>

## 为什么要学习全是括号的语言<a id="sec-1-1" name="sec-1-1"></a>

### Clojure 是好东西<a id="sec-1-1-1" name="sec-1-1-1"></a>

上世纪50年代的就有了lisp语言，都不能说它不是一门语言，因为他太多种方言了。虽然一直都不温不火，但是随着系统逻辑和计算越来越复杂，再加上分布式和并行计算。人们突然发现函数式是一个好东西，state is evil。目前比较流行的lisp方言是Clojure，Scheme。而选择Clojure是因为

-   专门为多线程并发编程设计
-   跑在JVM上，使部署变得简单
-   lisp语法太简单了，函数，函数，都是函数
-   动态类型，更灵活
-   数据结构都是Immutable，mutable is evil
-   与Java交互
-   丰富的第三方库

### 函数式是好东西<a id="sec-1-1-2" name="sec-1-1-2"></a>

OO并没有想象中的好，带状态和mutable的代码特别难推理，非常难读。需要特别多的上下文才能推理当前属于哪种状态，有哪些行为。如果再加上多线程，那就更难推理代码的行为了。

### 多态是好东西<a id="sec-1-1-3" name="sec-1-1-3"></a>

OO的多态的概念倒是有趣的好东西。一个函数在不同类型的参数能有不同的行为，使得我们的代码更灵活。

### 多线程是好东西如果用的对<a id="sec-1-1-4" name="sec-1-1-4"></a>

-   Immutablility 减少了很多多线程带来的问题
-   加锁只会阻塞并使事情更复杂，Clojure用更妙的方式解决资源共享问题。

## 搭建环境<a id="sec-1-2" name="sec-1-2"></a>

首先得有一个管理依赖的玩意，如Ruby的bundler，python的pip，js的npm。clojure用leiningen。

如果你用mac，简单的用brew安装leiningen

{lang="shell"}
~~~~~~~~
brew install leiningen
~~~~~~~~

clojure的编辑器我推荐使用emacs，如果你觉得emacs学习曲线太陡峭，那么[light table](http://lighttable.com/)是个不错的选择。

## 来试试不一样的Clojure数据结构<a id="sec-1-3" name="sec-1-3"></a>

### Number<a id="sec-1-3-1" name="sec-1-3-1"></a>

Cojure支持全面的数字类型，甚至包括分数。

{lang="clojure"}
~~~~~~~~
1/2
~~~~~~~~

### String<a id="sec-1-3-2" name="sec-1-3-2"></a>

字符串只能用双引号定义哦，字符串的连接不再是加号，而是str

{lang="clojure"}
~~~~~~~~
(str "What's your name? " "Han Meimei")
~~~~~~~~

### Vector<a id="sec-1-3-3" name="sec-1-3-3"></a>

向量是indexed的集合，用方括号初始化

{lang="clojure"}
~~~~~~~~
[1 2 3 4]
(vector 1 2 3 4)
~~~~~~~~

由于动态类型，还支持向量内的元素可以是任何类型

{lang="clojure"}
~~~~~~~~
(get [1 "2" {3 "4"}] 2)
~~~~~~~~

### List<a id="sec-1-3-4" name="sec-1-3-4"></a>

和vector类似，但是却稍微不同

{lang="clojure"}
~~~~~~~~
'(1 2 3 4)
(list 1 2 3 4)
~~~~~~~~

但是取元素的时候就和vector有所不同了

{lang="clojure"}
~~~~~~~~
(nth '(1 2 3 4) 2)
~~~~~~~~


