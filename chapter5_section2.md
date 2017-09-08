# 解决方案

iuap-security组件引入OWASP组织的开源项目ESAPI，利用ESAPI，平台实现了对跨站脚本攻击（XSS），sql脚本注入等安全问题的预防。 ESAPI具有一个安全接口集，其对每一种安全控制有一种参考实现并支持自定义实现。组件在ESAPI的基础上进行扩展。加入了对HTML、CSS、JavaScript、XML、URL等编码与解码，信息的加密解密，信息的摘要签名，防sql注入等功能的API。  
iuap-security组件通过可配置的方式提供ESAPI给开发人员使用，方便了业务开发人员使用，iuap-security提供了rest api的签名和验签，在调用端和服务端分别做信息的摘要和验证，确保数据的完整性，防止恶意篡改。
