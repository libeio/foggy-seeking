
## 寻雾启示
- [http协议的无状态与Cookie](寻雾启示/http协议的无状态与Cookie.md)
- [OSI七层参考模型的一种使用](寻雾启示/OSI七层参考模型与应用开发.md)
- [保守使用aio](寻雾启示/使用restbed异步发送请求问题.md)
- [try_lock的一种应用场景](寻雾启示/try_lock的应用场景.md)
- [对微服务中微的另一种理解](寻雾启示/对微服务中微的另一种理解.md)
- [直接异步与线程池的使用场景区分](寻雾启示/直接异步与线程池的使用场景区分.md)
- [smart_ptr也不错](寻雾启示/smart_ptr也不错.md)
- [原子变量-多线程利器](寻雾启示/简单的原子变量.md)
- [内存问题不止两个](寻雾启示/基于restbed的长连接服务端长时间运行时崩溃问题.md)
- [要在线程创建之后使用锁](寻雾启示/要在线程创建之后使用锁.md)
- [智能指针产生的coredump](寻雾启示/智能指针产生的coredump.md)
- [服务器性能优化方法](寻雾启示/服务器性能优化方法.md)
- [类实例中线程成员的释放问题](寻雾启示/类实例中线程成员的释放问题.md)

## 问题处理
- [unique_lock不及时释放](问题处理/unique_lock不及时释放.md)
- [编译问题](问题处理/编译问题.md)
- [编译时添加-Wall](问题处理/编译时添加-Wall.md)
- [套接字设置为非阻塞时的时刻](问题处理/非阻塞套接字设置.md)
- [模板参数无法推导](问题处理/模板参数无法推导.md)

## 编程随笔
- 子进程使用 exit 退出，进程内启动进程通过 signal 退出;
- 不要轻易使用同步回调，很多时候没有必要却会增加程序复杂度;
- 对稳定信号(signal∈[SIGRTMIN, SIGRTMAX])的屏蔽是没必要的;
- 通信端作为服务端时，一般对 SIGPIPE 信号进行屏蔽;
- 不要对一些对象结构体(尤其是包含 std::string 成员变量的结构体)使用 memset;
