# 解密

**请求方法**  
RSAPrivateKey privateKey = RSAUtils.getDefaultPrivateKey();  
byte[] data = RSAUtils.decrypt(privateKey, encryptBytes);  
**参数说明**

<table>
   <tr>
      <td>参数名</td>
      <td>类型</td>
      <td>说明</td>
   </tr>
   <tr>
      <td>privateKey</td>
      <td>RSAPrivateKey</td>
      <td>私钥</td>
   </tr>
   <tr>
      <td>encryptBytes</td>
      <td>byte[]</td>
      <td>要解密的内容的字节数组</td>
   </tr>
</table>

**返回值**  
解密后的内容，类型为字节数组。


