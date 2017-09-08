# 编码

数据编码分为多种形式，如html编码、javascript编码、css编码、sql编码等，它们主要是用来解决各类注入问题：xss注入、sql注入。除此之外，还有Base64编码，常用来将非ASCII字符的数据转换成ASCII字符  
请求方法
*	html编码  
String safe =IUAPESAPI.encoder().htmlEncode( input);
*	属性编码  
String safe =IUAPESAPI.encoder().htmlAttributeEncode (input);
*	js编码  
String safe =IUAPESAPI.encoder().javaScriptEncode ( input);
*	url编码  
String safe =IUAPESAPI.encoder().urlEncode (input);
*	css编码  
String safe =IUAPESAPI.encoder().cssEncode ( input);
*	sql注入示例  
String queryCondition = IUAPESAPI.encoder().sqlPreparedString( input,paras, DatabaseCodec.ORACLE);
*	base64  
String base64Text = IUAPESAPI.encoder().encodeForBase64(input);

**请求参数说明**

<table>
   <tr>
      <td>参数名</td>
      <td>类型</td>
      <td>说明</td>
   </tr>
   <tr>
      <td>input</td>
      <td>字符串</td>
      <td>要编码的内容</td>
   </tr>
</table>

**返回值**  
编码后的字符串。

