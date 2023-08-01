# 简介

Java Server Pages (JSP) 是一种由 Sun Microsystems 开发的用于创建动态网页的技术。它是 Java EE (Java Enterprise Edition) 技术的一部分，允许开发者在 HTML 中嵌入 Java 代码，从而实现动态内容的生成。

JSP 主要由两部分组成：静态数据和 JSP 元素。静态数据可以是任何类型的文本，包括 HTML、XML、SVG 等，而 JSP 元素是一些用于生成动态内容的特殊标记。



# 准备工作

- [JDK下载](https://www.oracle.com/technetwork/java/javase/downloads/index.html)
- [Tomcat下载](https://tomcat.apache.org/download-90.cgi#9.0.11)
- [Eclipse下载](http://www.eclipse.org/downloads/)



# 一、JAVA环境配置

## 1.安装JDK

此处我选择安装java11，当然你可以选择其他版本的

![image-20230708211053945](JSP环境搭建/image-20230708211053945.png)	



java安装完后找到其安装路径：`C:\Program Files\Java\jdk-11`

![image-20230710162722149](JSP环境搭建/image-20230710162722149.png)	



## 2.配置环境变量

创建系统变量`JAVA_HOME`，对应的值为jdk的安装路径

<img src="JSP环境搭建/image-20230708231801945.png" alt="image-20230708231801945" style="zoom:67%;" />	

​	

在系统变量Path处添加个变量值：`%JAVA_HOME%\bin`

<img src="JSP环境搭建/image-20230708231918642.png" alt="image-20230708231918642" style="zoom:67%;" />		



## 3.运行测试

打开cmd命令行，输入`java -version` ，若返回java的版本信息则表示环境变量配置成功

![image-20230708211940462](JSP环境搭建/image-20230708211940462.png)	



# 二、Tomcat配置

## 1.安装Tomcat

进入Tomcat的官网，此处我选择下载Tomcat9.0的Windows_x64版本

![image-20230708212936013](JSP环境搭建/image-20230708212936013.png)

<img src="JSP环境搭建/image-20230708213029531.png" alt="image-20230708213029531" style="zoom:67%;" />	



将下载的文件解压至自定目录，此处我解压至`C:\\apache-tomcat`

![image-20230708213306646](JSP环境搭建/image-20230708213306646.png)



## 2.配置环境变量

创建系统变量`CATALINA_HOME`, 对应的值为Tomcat的安装路径

<img src="JSP环境搭建/image-20230708232030968.png" alt="image-20230708232030968" style="zoom:67%;" />	

​	

在系统变量Path添加个变量值： `C:\apache-tomcat\bin`

![image-20230708213700033](JSP环境搭建/image-20230708213700033.png)



## 3.运行测试

打开cmd命令行输入`startup`,  返回结果如下图所示则代表Tomcat配置成功

<img src="JSP环境搭建/image-20230708232126561.png" alt="image-20230708232126561" style="zoom:67%;" />	



可以发现上述Tomcat控制台出现乱码情况，不过这是编码问题，不影响程序的正常使用，当然你也可以修改其编码格式，用记事本打开conf目录下的`logging.properties`，在其末尾处添上`java.util.logging.ConsoleHandler.encoding = GBK`

<img src="JSP环境搭建/image-20230710163952643.png" alt="image-20230710163952643" style="zoom:67%;" />	



再次执行`startup.bat`后就不会出现乱码了

<img src="JSP环境搭建/image-20230710164504305.png" alt="image-20230710164504305" style="zoom:67%;" />	



# 三、配置Eclipse

## 1.安装Eclipse

打开官网下载Eclipse IDE，选择`Eclipse IDE for Enterprise Java and Web Developers`

<img src="JSP环境搭建/image-20230709220507290.png" alt="image-20230709220507290" style="zoom:67%;" />	

<img src="JSP环境搭建/image-20230709220538955.png" alt="image-20230709220538955" style="zoom:67%;" />	



将文件解压至自定目录后，运行`eclipse.exe`，此处需设置eclipse的工作路径，填写默认即可		

![image-20230709220639008](JSP环境搭建/image-20230709220639008.png)



## 2.添加Tomcat环境

点击`Windows->Preferences`

<img src="JSP环境搭建/image-20230709220849049.png" alt="image-20230709220849049" style="zoom:67%;" />	



展开`Server`，点击`Runtime Environment`,  点击右上角的`Add`		

![image-20230709221024755](JSP环境搭建/image-20230709221024755.png)	



选择你安装的Tomcat版本, 随后点击`Next`

![image-20230709221219429](JSP环境搭建/image-20230709221219429.png)	



输入Tomcat的安装路径, 点击`Finish`

![image-20230709221321020](JSP环境搭建/image-20230709221321020.png)	



## 3.设置运行浏览器

点击`Windows->Preferences`, 搜索框输入"web"，找到`Web Browser`，这里我选择使用外部浏览器, 勾选上`Default system web browser`, 表示启用系统默认浏览器

![image-20230709222957727](JSP环境搭建/image-20230709222957727.png)





# 四、编写JSP程序

## 1.新建Dynamic Web Project项目

点击`New->Project`新建项目

![image-20230709223407003](JSP环境搭建/image-20230709223407003.png)	



选择项目类型是`Web->Dynamic Web Project`, 即表示动态网页

![image-20230709223519760](JSP环境搭建/image-20230709223519760.png)	



填写项目名称，项目路径我选择默认的，然后点击Finish

![image-20230710105704605](JSP环境搭建/image-20230710105704605.png)	



## 2.新建jsp文件

在项目的webapp目录新建jsp文件

![image-20230710110109558](JSP环境搭建/image-20230710110109558.png)



填写jsp文件的名称

![image-20230710112451617](JSP环境搭建/image-20230710112451617.png)	



编写jsp文件的代码，例如此处在body标签处写入“Hello World”

![image-20230710112533920](JSP环境搭建/image-20230710112533920.png)



## 3.运行jsp文件

点击`Run On Server`运行

![image-20230710112600014](JSP环境搭建/image-20230710112600014.png)



第一次运行需要设置指定的server，此处选择你下载的Tomcat版本，随后点击Finish

![image-20230710112637143](JSP环境搭建/image-20230710112637143.png)	



运行后会弹出浏览器并显示运行jsp的页面

<img src="JSP环境搭建/image-20230710112735301.png" alt="image-20230710112735301" style="zoom:67%;" />	



# 可能遇到的问题

## 1.Eclipse的Preferences处没有Server选项

如果你在`Windows->Preferences`中没有看到`Server`选项, 那么你可能安装的是`Eclipse IDE for java Developers`, 你需要再添加额外的插件来实现对服务器的支持, 可以通过`Help->Install New Software`来安装这些插件

![image-20230709221504102](JSP环境搭建/image-20230709221504102.png)



勾选上Web服务, 安装插件成功后会自动重启Eclipse

<img src="JSP环境搭建/image-20230709221820908.png" alt="image-20230709221820908" style="zoom:67%;" />	



## 2.没有webcontent目录

网上很多文章都说项目创建后会有一个WebContent目录，但是新版本eclipse创建的web项目是Maven结构的，是没有WebContent目录的，因此我们只需将jsp和html文件放到webapp下，jar文件放到INF的lib文件夹里就行了