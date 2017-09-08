# 加密

**请求方法 ** 
//首次生成公钥的示例  
KeyPair gk = RSAUtils.generateKeyPair();           
RSAPublicKey publicKey = RSAUtils.getDefaultPublicKey();

//调用方法进行加密  
byte[] encryptBytes = RSAUtils.encrypt(publicKey, input.getBytes());  
**参数说明**

<table>
   <tr>
      <td>参数名</td>
      <td>类型</td>
      <td>说明</td>
   </tr>
   <tr>
      <td>publicKey</td>
      <td>RSAPublicKey</td>
      <td>公钥</td>
   </tr>
   <tr>
      <td>input</td>
      <td>byte[]</td>
      <td>要解密的内容的字节数组</td>
   </tr>
</table>

**返回值**  
加密后的二进制数组。

