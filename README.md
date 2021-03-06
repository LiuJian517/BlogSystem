# BlogSystem
使用Django制作的一款博客系统

![详情页](https://github.com/guoruibiao/BlogSystem/raw/master/BeautifyShow/%E5%8A%A0%E5%85%A5%E4%BA%86Bootstrap%E7%9A%84%E5%8D%9A%E6%96%87%E7%95%8C%E9%9D%A2.png)

![列表页](https://github.com/guoruibiao/BlogSystem/raw/master/BeautifyShow/%E5%8A%A0%E5%85%A5%E4%BA%86Bootstrap%E7%9A%84%E5%8D%9A%E5%AE%A2%E5%88%97%E8%A1%A8%E7%95%8C%E9%9D%A2.png)



## 功能

用户可以发布博客，删除修改博客；
博客可以贴标签，可以被分类
博客可以被评论等等

## 基础版

基础班使用基础的Django创建，实现基础的博客系统功能

## 美化版
美化版使用了Bootstrap进行了页面的美化。可以对比仓库中的图片，效果改观不少！

## 进阶版
进阶版对美化没有做过多的处理，而是添加了用户注册以及用户登录的功能。注册需要管理员进行审核，并添加相关的权限，通过后就可以正常
的使用本博客系统了。

## 数据库
数据库使用的是Python2.7自带的sqlite3.挺方便的。

### 写在后面

这个程序可谓是简单易懂，可以参照我的博文进一步阅读哦[博客系统构建](http://blog.csdn.net/Marksinoberg/article/details/51591005)

### 难点

我所认为的里面最让人难于理解的估计就是url反转了，下面单独的拿出来讲解一下。
- {% url 'blog_get_blogs' %} 可以看作是 reverse 方法的“模板语言”版，其作用是根据 URLConf 中的 name 定义对 url 进行反解析，转换成真实的 URL 地址。比如这里在转换之后会变成 “/”。如果所指定的 url 定义中包含参数，则需要将参数跟在后面，如 {% url 'blog_get_detail' blog.id %}；或者参考下面的这篇文章[reverse 应用在选票系统上](http://www.cnblogs.com/fnng/p/4855743.html)
- 观察表单的内容，{% csrf_token %} 用于防跨域请求，可参考一些关于 CSRF 相关的资料并阅读 Django 官方文档关于这一块实现的描述。{% for field in form %}{% endfor %} 是对表单的各个 field 进行迭代并生成相应的表单元素，并对校验过程中出现的错误进行显示以提示用户做相应的修改。最后还生成一个 button 用于点击提交评论。

### 最后

鉴于本人能力有限，欢迎各位对代码中存在的问题进行批评指正！
