# RestAPI签名

在请求端，根据URL参数（含ts值）、请求端IP地址、表单参数以及Content-Length的大小进行生成签名sign。  
SignProp prop = SignPropGenerator.genSignProp(url);  
signProp.setIp(ip);  
//post请求时需要  
signProp.setPostParamsStr(PostParamsHelper.genParamsStrByMap(parameter));  
signProp.setContentLength(ContentLength);  
String sign = ClientSignFactory.getSigner(cert).sign(prop);  
注意：如果配置多份客户端证书，需要在getSinger的时候指定前缀,示例如下：
ClientSignFactory.getSigner("bpm")

**SignProp中包含的参数说明**
<table>
   <tr>
      <td>参数名</td>
      <td>必选</td>
      <td>类型</td>
      <td>说明</td>
   </tr>
   <tr>
      <td>ts</td>
      <td>true</td>
      <td>字符串</td>
      <td>请求发出的时间戳，在请求的url中</td>
   </tr>
   <tr>
      <td>ip</td>
      <td>false</td>
      <td>请求端IP地址</td>
      <td>请求端IP地址</td>
   </tr>
   <tr>
      <td>postParamsStr</td>
      <td>false</td>
      <td>字符串</td>
      <td>POST表单参数Map生成的字符串，可以调用PostParamsHelper中的方法生成</td>
   </tr>
   <tr>
      <td>contentLength</td>
      <td>false</td>
      <td>字符串</td>
      <td>HttpServletRequest中取得的Content-Length的值</td>
   </tr>
</table>

**返回值**  
sign 生成的验证签名,类型为字符串。
