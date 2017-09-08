# RestAPI验签

在服务端，首先比较当前时间ts’与ts的大小，如果其差值不大于DEFAULT_EXPIRED，则从HTTP请求中获得时间戳ts、URL参数、请求的来源IP地址、表单参数以及ContentLength的大小生成sign’。此时如果sign与sign’相同，则签名验证通过  
SignProp prop = SignPropGenerator.genSignProp(url);  
//服务端需要获取客户端的真实ip  
signProp.setIp(ip);  
//post请求时需要  
signProp.setPostParamsStr(PostParamsHelper.genParamsStrByMap(request));  
//在服务端获取请求的contentLength  
signProp.setContentLength(contentLength);

DemoServerVirifyFactory factory = new DemoServerVirifyFactory();  
Boolean result = factory.getVerifier(appid).verify(sign, prop);  
DemoServerVirifyFactory为开发者实现的类，需要实现获取证书的方法。  

**参数说明**

<table>
   <tr>
      <td>参数名</td>
      <td>类型</td>
      <td>说明</td>
   </tr>
   <tr>
      <td>appid</td>
      <td>字符串</td>
      <td>服务端存储的证书中对应的客户端的唯一标识</td>
   </tr>
   <tr>
      <td>sign</td>
      <td>字符串</td>
      <td>请求中传入的sign，用来与服务端生成的sign进行对比</td>
   </tr>
   <tr>
      <td>prop</td>
      <td>SignProp</td>
      <td>需要验证签名的参数集合对象</td>
   </tr>
</table>

**返回值**  
验证是否成功，类型为boolean。
