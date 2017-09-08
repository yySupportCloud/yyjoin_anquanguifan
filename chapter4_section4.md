# WEB安全防范

*	Cookie的安全防范：  
1.存储于cookie中的敏感数据必须加密。  
2.没有特殊要求下，尽量使用会话cookie(非持久化)。  
3.如果使用持久化cookie应该设置cookie超时。  
4.激活cookie安全传输，表示创建的 cookie 只能在https连接中被浏览器传递到服务器端进行会话验证，如果是http连接则不会传递该信息。

*	必须设置session的超时时间。
*	构建统一的错误处理页面。
*	多线程中线程安全的防范：  
1.尽量少用静态（static）变量和static方法。（除了静态常量：static final constants）。  
2.尽量多线程框架(java.util.concurrent)构建多线程同步机制。  
3.使用ThreadLocal避免多个线程之间类成员的共享冲突。  
4.如非必要，不要使用synchronized关键字。必须要使用synchronized时，应将同步范围最小化，即将同步作用到最需要的地方，避免大块的同步块或方法等。

*	增加Referer的检查，防止非法访问。Referer是HTTP Header中的一个字段，当浏览器想服务器发送请求时，Referer用来通知服务器请求发起的位置。
