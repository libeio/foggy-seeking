
## 问题描述
- 调用 restbed 同步发送(restbed::Http:sync)http请求时，出现崩溃(Core Dump)或异常(请求
  得不到响应，表现为状态码为0)。

## 问题场景与原因分析
- 多线程发送队列内的 http 请求，通过锁保护请求队列。大致代码如下:
  ```c++
    // 线程
    while (1) {
        std::unique_lock<std::mutex> guard_in(mtx);
        cond.wait(guard_in, ...);
        
        auto req = reqQue.front();
        reQue.pop();
        guard_in.unlock();      /** 主动释放锁 */
        
        /** deal with sth before send req */
        auto response = restbed::Http::sync(req);
        /** deal with sth after recv the response */
    }
  ```
- gdb 调试发现，在调用 sync 时出错。错误原因有两个，一个是套接字也是共用资源，没有对
  其进行保护。还有一个原因是 sync 实质上也是异步发送，如下:
  ```c++
    const shared_ptr< Response > Http::sync( const shared_ptr< Request > request, const shared_ptr< const Settings >& settings )
    {
        auto response = Http::async( request, nullptr, settings );
        response.wait( );
        
        return response.get( );
    }
  ```
  只不过是异步发送之后原地等待。 async 内部引用了类似于 boost 的通信机制，实现了真正的并行发送。

## 解析办法
- 对 sync 也进行锁保护。

## 结尾
- 因为端口是公共资源，如果想要提高发送效率，可以尝试采用多端口发送。