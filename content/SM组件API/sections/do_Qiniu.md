---
title: do_Qiniu 组件
---

### do_Qiniu 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Qiniu)
 七牛云自主研发的分布式对象存储服务，提供高可靠、强安全、低成本、可扩展的存储服务，满足各类存储需求

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>异步方法</font>  |[upload](#upload)| 上传文件
<font color ='#0092db'>异步方法</font>  |[download](#download)| 从七牛云下载文件
<font color ='#e96900'>事件</font>  |[progress](#progress)| 响应进度事件,文件大小和当前上传或者下载的进度

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=upload><font color ='#0092db'>**upload**</font></span>: 上传文件

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **filePath** |<font color ='#808000'>**string**</font> | 是 | |支持data://目录文件
  **accessKey** |<font color ='#808000'>**string**</font> | 是 | |用户凭证是七牛云存储颁发给用户的标识。用户将用户凭证放入访问请求，以便七牛云存储识别访问者的身份
  **secretKey** |<font color ='#808000'>**string**</font> | 是 | |是七牛云存储颁发给用户，用于对访问请求签名的字串。用户使用签名密钥对访问请求的核心要素进行签名，获得请求认证令牌。用户将令牌随同访问请求一起发送至七牛云存储服务，七牛云存储将对令牌进行校验，以确认用户请求的合法性
  **bucket** |<font color ='#808000'>**string**</font> | 是 | |存储空间可以有多个,根据名称存储到对应的存储空间里面
  **saveName** |<font color ='#808000'>**string**</font> | 否 | |文件上传到七牛云之后要保存的名称，也就是在七牛云存储里面显示的名称，缺省为原文件名
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 上传成功返回true,否则返回false
- 说明: 根据用户的accessKey,secretKey以及bucket(七牛存储空间名称)，生成uploadToken，然后根据uploadToken上传文件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=download><font color ='#0092db'>**download**</font></span>: 从七牛云下载文件

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **domainName** |<font color ='#808000'>**string**</font> | 是 | |
  **fileName** |<font color ='#808000'>**string**</font> | 是 | |
  **path** |<font color ='#808000'>**string**</font> | 是 | |下载到本地的文件的全路径，只支持data://
  **accessKey** |<font color ='#808000'>**string**</font> | 否 | |用户凭证是七牛云存储颁发给用户的标识。用户将用户凭证放入访问请求，以便七牛云存储识别访问者的身份
  **secretKey** |<font color ='#808000'>**string**</font> | 否 | |是七牛云存储颁发给用户，用于对访问请求签名的字串。用户使用签名密钥对访问请求的核心要素进行签名，获得请求认证令牌。用户将令牌随同访问请求一起发送至七牛云存储服务，七牛云存储将对令牌进行校验，以确认用户请求的合法性
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 下载成功返回true，下载失败返回false
- 说明: 文件下载是一个标准的 HTTP GET 过程，如果从公开空间下载文件不需要提供用户凭证和签名密钥，私有空间则必须提供文件来源方的用户凭证和签名密钥
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=progress><font color ='#e96900'>**progress**</font></span>: 响应进度事件,文件大小和当前上传或者下载的进度

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回值包含两个节点{fileSize:'23234245',percent:'20'}单位分别为kB和%
- 说明: 响应进度事件,文件大小和当前上传或者下载的进度
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


