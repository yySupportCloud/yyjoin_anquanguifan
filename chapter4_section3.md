# 敏感数据的安全防范

*	不能任意在Cookie、Session、ServletContext中存放数据，对于这些对象中存放的数据，必须有统一定义、说明、Lifecycle的管理等。
*	对于敏感信息都必须保障其私密性。在页面显示、操作交互中不可避免的会有一些如用户的标识信息、密码、帐号信息、涉及的金额信息等敏感数据(保密性的数据)的存在。为保障这些数据不被曝露而提高安全性，我们要做到所有敏感信息必须进行加密处理，不能以明文的形式存在于任何网络、内存及其它持久化介质中(如：数据库、文件磁盘系统等)。
*	所有的密码、key、帐号等机密信息都不能在URL中传递。
*	所有的密码、key、银行账号等机密信息都不能存储到Cookie，Session、ServletContext中。
*	防止信息泄漏：  
1.在系统上线使用的log level对应的日志输出中不允许包含任何密码、key、账号等机密信息。  
2.代码中不允许存留可用的system.out/err.print语句。  
3.不允许将系统产生的错误异常信息直接显示给用户，需要有统一的错误处理。
*	尽量减少不必要的信息传递。在信息的传递过程中，如果当前Step中的对象、对象的属性、参数等在下一个Step中不需要，则不要再做传递，甚至可以显式的销毁。这样可以有效的减少信息被截获的机率，特别是敏感数据(例如用户密码、账户信息等等)。