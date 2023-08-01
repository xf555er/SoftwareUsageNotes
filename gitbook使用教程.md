# 简介

Gitbook 是一个平台，允许用户创建和分享内容丰富的在线书籍。它有一个用户友好的界面，可以快速地写作、编辑和发布你的电子书。这里是一个按照 Gitbook 的基本步骤



# 与github同步

## 1.创建space

打开[GitBook官网](https://www.gitbook.com)，这里我选择使用github账号来登录，当然你也可以自己新建一个账号

![image-20230725161711515](gitbook使用教程/image-20230725161711515.png)



点击左下角的加号，选择`New space`创建一个新的Gitbook空间

![image-20230725111536004](gitbook使用教程/image-20230725111536004.png)



## 2.安装github插件

点击上方的`integrations`，随后选择`Github Files`

![image-20230725111637058](gitbook使用教程/image-20230725111637058.png)

<img src="gitbook使用教程/image-20230725111643459.png" alt="image-20230725111643459" style="zoom:67%;" />



点击`Install`安装github的插件

<img src="gitbook使用教程/image-20230725111938696.png" alt="image-20230725111938696" style="zoom:67%;" />				



安装完插件后，需点击`Authorize`授予gitbook与github同步的权限，随后会弹出一个浏览框(可能需登录你的github)，点击`Authorize GitbookIO`

<img src="gitbook使用教程/image-20230725112246192.png" alt="image-20230725112246192" style="zoom:67%;" />	

<img src="gitbook使用教程/image-20230725112329817.png" alt="image-20230725112329817" style="zoom:67%;" />	



## 3.同步github

返回space页面，点击`Sync with Github`，表示此space要与github同步

![image-20230725155306916](gitbook使用教程/image-20230725155306916.png)



在`Synchronize with Git`的`Provider`处，勾选上`Github`

<img src="gitbook使用教程/image-20230725155400908.png" alt="image-20230725155400908" style="zoom:67%;" />	



在`Configuration`处，点击`Connect with Github`，随后选择`Install Github application`

<img src="gitbook使用教程/image-20230725155427566.png" alt="image-20230725155427566" style="zoom:67%;" />	

<img src="gitbook使用教程/image-20230725155453201.png" alt="image-20230725155453201" style="zoom:67%;" />	



弹出页面让你安装Gitbook，点击`Install`

<img src="gitbook使用教程/image-20230725155545507.png" alt="image-20230725155545507" style="zoom:67%;" />	



选择你的Github账户、仓库以及分支，随后点击`synchronize`开始同步

<img src="gitbook使用教程/image-20230725155718068.png" alt="image-20230725155718068" style="zoom:67%;" />	

<img src="gitbook使用教程/image-20230725155817170.png" alt="image-20230725155817170" style="zoom:67%;" />	



同步完成如下图所示

![image-20230725155905395](gitbook使用教程/image-20230725155905395.png)	



## 4.生成space的url

在space可以看到，github文章的内容同步到gitbook来了，若想让别人看到，还需点击右上角的`Share`

![image-20230725160400226](gitbook使用教程/image-20230725160400226.png)



在`Publish to the web`处勾选上`Publish this space to the web`，随后它会生成你笔记的url链接，例如此处我是https://aptboys.gitbook.io/demo1

![image-20230725160445935](gitbook使用教程/image-20230725160445935.png)				



访问生成的url链接，效果如下图所示

![image-20230725160714932](gitbook使用教程/image-20230725160714932.png)			



# 博客搭建指南

## 1.自定义域名

点击你创建的组织的设置选项，例如此处我创建的组织为AptBoys，我就点击`AptBoys Settings`

<img src="gitbook使用教程/image-20230731161523335.png" alt="image-20230731161523335" style="zoom:67%;" />



在General选项块处找到`Custom domain`，点击`Edit domain`自定义你博客的域名

![image-20230731161826751](gitbook使用教程/image-20230731161826751.png)		







填写你的三级域名, 例如此处我的是`www.henry666.xyz`，域名`henry666.xyz`是我在godaddy上申请的(不用域名备案)

<img src="gitbook使用教程/image-20230731162005376.png" alt="image-20230731162005376" style="zoom:67%;" />		





将DNS记录的字段及其对应的值添加至你域名的DNS管理记录中, 此处需添加的dns记录是CNAME类型的www, 指向gitbook网址

![image-20230731162704872](gitbook使用教程/image-20230731162704872.png)	![image-20230731163123174](gitbook使用教程/image-20230731163123174.png)



最后一步是验证你的域名是否正确配置

<img src="gitbook使用教程/image-20230731163220710.png" alt="image-20230731163220710" style="zoom:67%;" />		



## 2.发表博客内容

创建`Collection`，可用于存放多个space，这样方便与github仓库的文章进行同步

<img src="gitbook使用教程/image-20230731164636125.png" alt="image-20230731164636125" style="zoom:67%;" />		



将创建的集合发布到Web上

<img src="gitbook使用教程/image-20230731164840656.png" alt="image-20230731164840656" style="zoom:67%;" />	



接下来这一步十分重要，需将集合内的space发布在Web上，此处选择`Publish in collection`	

![image-20230731165021217](gitbook使用教程/image-20230731165021217.png)



最终博客效果如下图所示:

![image-20230731165207911](gitbook使用教程/image-20230731165207911.png)



## 3.设置域名默认页面

转到设置页面, 找到`Default Content`，点击`Change default content`修改域名默认页面

<img src="gitbook使用教程/image-20230731232149280.png" alt="image-20230731232149280" style="zoom:67%;" />



选择你之前创建的Collection

<img src="gitbook使用教程/image-20230731232255893.png" alt="image-20230731232255893" style="zoom:67%;" />				



当你访问你的域名时，则会跳转至`Collection`页面。比如我访问我的域名`www.henry666.xyz`，它会自动跳转至`www.henry666.xyz/henryblog/`

![image-20230731232327530](gitbook使用教程/image-20230731232327530.png)	



## 4.界面设置

点击`Collection Customization`自定义博客界面, 在`Title&Icon`可以设置你的博客标题和显示图标, 在左边栏可以实时看到修改后的博客界面

![image-20230801155139981](gitbook使用教程/image-20230801155139981.png)



`Default space`可以设置博客的默认space, `Themes`设置博客主题

<img src="gitbook使用教程/image-20230801155333207.png" alt="image-20230801155333207" style="zoom:67%;" />			



在`Configure`处可勾选上`Enable lens semantic search`, 用于启动AI搜索引擎

![image-20230801155426822](gitbook使用教程/image-20230801155426822.png)

​	

## 注意事项

1.github仓库的markdown文件名最好不要有空格，换句话来说你存放图片的文件目录不能是有空格的，这样你的图片文件是无法在页面上显示的

2.后面遇到再写吧，嘻嘻



# End

​	

