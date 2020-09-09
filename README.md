# cos_pics
一批比较安全的妹子图，目前约13000张。

## 注意事项
* 国内请使用jsdelivr.net加速，否则速度很慢。只要在文件的仓库路径前添加`https://cdn.jsdelivr.net/gh/ipchi9012/cos_pics@v1/`即可，比如：
  * cos_index.js -> https://cdn.jsdelivr.net/gh/ipchi9012/cos_pics@v1/cos_index.js
  * 0a16f8a52af7/20140122095237390.jpg -> https://cdn.jsdelivr.net/gh/ipchi9012/cos_pics@v1/0a16f8a52af7/20140122095237390.jpg
* 每100张图片有一个索引js文件，前端可以用jsonp方式引用，文件名和jsonp中的函数名。后端可以去掉前面的`cos_xxxx(`和最后的`)`后作为普通json解析
* cos_index.js是总目录，包含所有索引文件的名字列表
* 为了减小图片空间占用，所有图片均为30万像素（约640x480），JPEG压缩质量为75，色度抽样值为4:2:0
