
## 寻雾启示
- [http协议的无状态与Cookie](http协议的无状态与Cookie.md)
- [OSI七层参考模型的一种使用](OSI七层参考模型的一种使用.md)
- [restbed同步不同步](restbed同步不同步.md)
- [try_lock的应用场景](try_lock的应用场景.md)
- [对微服务中微的另一种理解](对微服务中微的另一种理解.md)
- [直接异步与线程池的使用场景区分](直接异步与线程池的使用场景区分.md)

## 问题处理
- [unique_lock不及时释放](unique_lock不及时释放.md)

## 编程随笔
- 子进程使用 exit 退出，进程内启动进程通过 signal 退出;
- 不要轻易使用同步回调，很多时候没有必要却会增加程序复杂度;
- 对稳定信号(signal∈[SIGRTMIN, SIGRTMAX])的屏蔽是没必要的;
- 通信端作为服务端时，一般对 SIGPIPE 信号进行屏蔽;
- 不要对一些对象结构体(尤其是包含 std::string 成员变量的结构体)使用 memset;
