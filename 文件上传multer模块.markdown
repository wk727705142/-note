# 文件上传

  ## 文件上传服务端
```
    使用中间件 multer
    
    下载multer   npm install multer --save
    
    引入multer并使用   require('multer')
    
    文档地址：https://github.com/expressjs/multer/blob/master/doc/README-zh-cn.md

```
  ## multer使用api
    ```
      1. 作为express的中间件，其作用是把表单中的文件读取到，并保存，把文件的信息保存在req.file中；
      
      2. 引入multer模块，该模块是一个构造函数，通过该构造函数生成一个上传文件实例，生成实例时，需要传入一个配置对象
      
          var multer = require('multer')
          
          var upload = multer(options)
          
      3. 关于options的配置项的简单使用，仅设置文件存储路径即可   {dest:'文件存储路径'}
      
      4. 文件上传实例upload可以使用三个方法
      
            upload.single(文件name字段) 
           
            upload.array(文件name字段，上传文件最大数量)
            
            upload.fields({name:文件name字段,maxCount:上传文件最大数量})
            
      5. 查看上传文件的信息
      
         req.file或者req.files
      
    ```
## 每个上传的文件有如下信息
| 属性        |     |
| --------   | -----:   |
| fieldname |Field name 由表单指定 |
| originalname |用户计算机上的文件的名称      |
| encoding| 文件编码|
|mimetype|文件的MIME类型|
|size|文件大小（字节单位）|
|destination|保存路径|
|filename|保存在destination中的文件名|
|path|已上传文件的完整路径|
|buffer|一个存放了整个文件的Buffer|


## 文件上传浏览器端
  ```
    新特性FileReader
    1 . 生成实例   var fr = new FileReader();
    2 . fr.readAsDataURL(file) 读取文件，并以URL的形式保存在fr的result中
    3. fr.onload事件，在文件读取完成触发；

  ```
