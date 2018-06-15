# zphupload.js
文件上传拖拽效果，以及图片，MP3，MP4格式的预览，ajax上传

1.创建upload.html,最后引入zphupload.js(注意放在最后)
```html
<meta charset="utf-8">
<div  id="drop_area" >将图片拖拽到此</div>  
<button onclick="zphxhrupload('upload.php')">ajax上传</button> 
<script src="zphupload.js"></script>
```
2.创建upload.php
```php
<?php  
    print_r($_FILES["file"]);  
    $name = $_FILES["file"]["name"]; //中文可能乱码使用iconv函数  
    move_uploaded_file($_FILES["file"]["tmp_name"],iconv("UTF-8","gb2312",$name));  
?>  
```

