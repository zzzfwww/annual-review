# Golang

## Goland 使用技巧
1. goland集合git的工作流处理，管理分支，拉取分支，提交mr，一气呵成都可以完成。
2. 断点调试技巧，需要debug的点打上断点，然后运行程序到断点，还可以选择`Evaluate Expression`,选择想要实时计算的表达式，这样就非常方便看特定场景下某些具体变量的具体值
3. 还有一些技巧，[skill](https://github.com/zzzfwww/daydayup/blob/master/skills/idea-goland-keymap.md)，都是总结是实践出来的，也很值得推荐

## go-zero
go-zero库是这一年一直在仔细研究的库，里面有很多宝藏型的工具，这些工具也在我工作中使用到，并且直接拿来用就可以解决真实的业务场景的问题，内心的满足感非常足

### rest chain
restful api 自动注入中间件源码解析，并且实验其中核心点，总结和实验过程[process](https://github.com/zzzfwww/daydayup/tree/master/22-10-29-alice)

### 熔断器
go-zero熔断器在框架内部直接集成，访问redis，mysql以及接口调用都默认开启，同时也在出现错误的时候直接使用，详细看了一下源码，里面的实现逻辑就是使用滑动窗口统计一个时间段内的成功和失败的请求，然后通过成功失败的请求个数带入一个Google SRE算法，计算是否要丢弃请求还是接收请求，其中有一个关键点，默认配置如果被调用服务qps都不支持5就出错，就没有fallback逻辑，马上报错。

具体设计和实现可以看源码，以及这篇[文章](https://zhuanlan.zhihu.com/p/559244793)

### 服务发现和注册
以前公司工作的时候一直觉得这块内容不是特别清晰，但是看完go-zero里面的服务发现和设计的源码以及文章之后，发现原来业界对于这种场景的通用解决方案和实施内容也有很熟悉的理解，其中go-zero内置的就是p2c的服务发现逻辑，和Nginx里面的负载均衡算法一致

具体文章可以[参考](https://zhuanlan.zhihu.com/p/547449846)

### zero官网学习
在闲来无事的时候，查看go-zero官网，里面发现了一些内容，其中有一个book项目，本意想要学习一下jwt的token在不同服务之间传递的，但是在原本按照官网逻辑去实现此功能，发现官网有错误，所以自己clone一份出来，然后做对应的修改，最后完成jwt中间件的使用和调试[book](https://github.com/zzzfwww/daydayup/tree/master/22-11-05-zero-book)

### 常用封装技巧
不管是sql，sqlc,rollwindow,breaker，go-zero里面设计的核心点，都是基于函数参数进行通用化封装，这也就是在go语言里面，函数是一等公民的具体框架实现中的体现，理解之后还是觉得这种设计确实够精妙，在整个go-zero里面的设计一直保持万俊峰的Keep it simple 原则，有空多研究这种源码，看懂之后就是一种享受

## 其他场景

### 极致秒杀场景

在极致秒杀场景，除了需要引入消息中间件来进行相应的削谷填峰的处理之外，还需要一些特殊的工具，这种工具就是可以batch一大片请求，再给消息队列发送。这样还能让消息队列的负载和压力不至于被压死

实现这种工具也有一个已有的轮子[link](https://github.com/zzzfwww/daydayup/tree/master/22-08-21-batcher)

## 明年规划
1. 继续深度参与各种项目
2. 深究源码，各种框架的最核心源码都需要继续深入
3. 使用go-zero的生态，完成工作中的内容
4. 云原生的技术栈继续深入
