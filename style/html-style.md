```html
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <meta http-equiv="X-UA-Compatible" content="IE=Edge,chrome=1">
    <link href="./demo.css" rel="stylesheet">
    <meta name="renderer" content="webkit">
    <meta name="description" content="">
    <meta name="keyword" content="">
    <!-- 基础库 -->
    <script src="./basic.js"></script>
  </head>
  <body>
    <!-- 业务脚本 -->
    <script src="./demo.js"></script>
  </body>
</html>
```
## 规范
### 两个空格
### 标签统一小写
### 属性统一双引号
### Boolean 属性不使用 Value 值，统一出现就是 True，不出现就是 False.
### 自定义属性使用 data- 前缀
### 属性属性按照：class、id或name、data-*以及其它，有一定 gzip 压缩率提升
### 自合并标签统一不加 /
### 多媒体添加不支持属性或值
  1. img 增加 alt 属性
  2. object、audio 和 video 增加不支持说明


## 参考
[CodeGuide](http://codeguide.co/)
