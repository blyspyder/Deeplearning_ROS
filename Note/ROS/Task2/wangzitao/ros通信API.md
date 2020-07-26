# 话题
## 定义消息类型
### 编译配置
>[wiki](http://wiki.ros.org/msg#Building_.msg_Files)

### `.msg`文件
>[数据类型](http://wiki.ros.org/std_msgs)

    msg_file:=(type field_name \n)*

    type:=[
        bool
        int8
        uint8
        int16
        uint16
        int32
        uint32
        int64
        uint64
        float32
        float64
        string
        time
        duration
        array
    ]
    array:=[
        type[number]
        type[]
    ]
## 发布者
```cpp
template <class M>//消息类型
    Publisher advertise(
        const std::string& topic,//话题
        uint32_t queue_size,//缓冲队列大小
        bool latch = false//是否保存最后一个消息,并发给系统中的新订阅者
        )
```
## 订阅者
```cpp
template<class M>//消息类型
    Subscriber subscribe(
        const std::string& topic,//话题
        uint32_t queue_size,//缓冲队列大小
        void(*fp)(const boost::shared_ptr<M const>&),//消息处理程序可以用函数指针/闭包/函数指针+对象
        const TransportHints& transport_hints = TransportHints()//通信选项
        )
```
# 服务
## 数据类型
### 编译配置
>[wiki](http://wiki.ros.org/cn/ROS/Tutorials/CreatingMsgAndSrv#A.2BT391KA_srv)
### `.srv`文件
    srv_file:=(
            (type field_name \n)* 
            ---
            type
    )
## 服务端
```cpp
template<class MReq/*请求类型*/, class MRes/*响应类型*/>
  ServiceServer advertiseService(
       const std::string& service,//服务路径
       bool(*srv_func)(MReq&, MRes&)//服务处理程序可以用函数指针/闭包/函数指针+对象
       )
```
`advertiseService` 函数有多个重载,可以用函数指针/闭包/函数指针+对象来注册服务处理程序.
## 客户端
### 获取服务
```cpp
template<class Service>
  ServiceClient serviceClient(
      const std::string& service_name, //服务路径
      bool persistent = false, //是否持久连接
      const M_string& header_values = M_string()//连接握手参数
      )
```
### 调用服务
```cpp
template<class Service>//服务类型,包含请求和响应
  bool call(Service& service)
```