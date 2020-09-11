# cos_pics
一批比较安全的妹子图，约13000张。<br/>
本仓库的初衷是提供QQ机器人使用，避免QQ账号因为发涉黄图片被封，因此已经过作者的筛选，去掉了暴露过多和姿势太过诱惑的图片。

## 注意事项
* 国内请使用jsdelivr.net加速，否则速度很慢。只要在文件的仓库路径前添加`https://cdn.jsdelivr.net/gh/ipchi9012/cos_pics@latest/`即可，比如：
  * `cos_index.js` -> `https://cdn.jsdelivr.net/gh/ipchi9012/cos_pics@latest/cos_index.js`
  * `cos_0011.js` -> `https://cdn.jsdelivr.net/gh/ipchi9012/cos_pics@latest/cos_0011.js`
  * `0a16f8a52af7/20140122095237390.jpg` -> `https://cdn.jsdelivr.net/gh/ipchi9012/cos_pics@latest/46ec99606114/1496026269124938.jpg`
* 每100张图片有一个索引文件，名为cos_xxxx.js，前端可以用jsonp方式跨域引用，文件名和jsonp中的函数名相同。见如下例程：
  ```js
  window['cos_0011'] = function(arr) { // 动态添加全局函数，函数名需要和后面的脚本文件名匹配
    for (var img of arr) { // 遍历索引对象中所有元素
      var el = document.createElement('img') // 动态创建img元素
      el.src = 'https://cdn.jsdelivr.net/gh/ipchi9012/cos_pics@latest/' + img.path // 使用jsdelivr CDN引用图片
      document.getElementById('imgContainer').appendChild(el) // 添加到图片容器元素中
    }
  }
  var sc = document.createElement('script') // 动态创建一个模块类型的脚本元素
  sc.type = 'module'
  sc.src = 'https://cdn.jsdelivr.net/gh/ipchi9012/cos_pics@latest/cos_0011.js' // 注意此处脚本名与前面函数名必须一致
  document.getElementsByTagName('head')[0].appendChild(sc) // 动态添加到文档头部
  ```
* 后端使用则可以删除js源文件前面的`"cos_xxxx("`和最后的`")"`后作为普通json解析。具体可参考[此仓库](https://github.com/rockswang/meizi.opq)。
* cos_index.js是总目录，包含所有索引文件的名字列表，jsonp用法参考索引文件
* 为减小空间和带宽占用，所有图片均为30万像素（约640x480），JPEG压缩质量为75，色度抽样值为4:2:0
