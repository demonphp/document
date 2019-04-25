### Tomcat

###Tomcat安装

1. 直接解压 ，然后找到bin/startup.bat

2. 可以安装

启动之后，如果能够正常看到黑窗口，表明已经成功安装。 为了确保万无一失， 最好在浏览器的地址栏上输入 ： http://localhost:8080 , 如果有看到内容 就表明成功了。

3. 如果双击了startup.bat,  看到一闪而过的情形，一般都是 JDK的环境变量没有配置。


###Tomcat目录介绍

bin##

		> 包含了一些jar ,  bat文件 。  startup.bat

conf##
​
		tomcat的配置 	server.xml  web.xml

lib

	  	tomcat运行所需的jar文件

logs

		运行的日志文件
temp

		临时文件

webapps##

		发布到tomcat服务器上的项目，就存放在这个目录。

work(目前不用管)

		jsp翻译成class文件存放地
​


##如何把一个项目发布到tomcat中

> 需求： 如何能让其他的电脑访问我这台电脑上的资源 。 stu.xml

	localhost : 本机地址

###1.  拷贝这个文件到webapps/ROOT底下， 在浏览器里面访问：

		http://localhost:8080/stu.xml

	* 在webaps下面新建一个文件夹xml  , 然后拷贝文件放置到这个文件夹中

​
		http://localhost:8080/xml/stu.xml

		http://localhost:8080 ： 其实对应的是到webapps/root
		http://localhost:8080/xml/ : 对应是 webapps/xml

		使用IP地址访问：

		http://192.168.37.48:8080/xml/stu.xml

###2. 配置虚拟路径


使用localhost：8080 打开tomcat首页， 在左侧找到tomcat的文档入口， 点击进去后， 在左侧接着找到 Context入口，点击进入。

	http://localhost:8080/docs/config/context.html

1. 在conf/server.xml 找到host元素节点。

2. 加入以下内容。


   		<!-- docBase ：  项目的路径地址 如： D:\xml02\person.xml
   		path : 对应的虚拟路径 一定要以/打头。
   		对应的访问方式为： http://localhost:8080/a/person.xml -->
   		<Context docBase="D:\xml02" path="/a"></Context>

3. 在浏览器地址栏上输入： http://localhost:8080/a/person.xml


###3. 配置虚拟路径

1. 在tomcat/conf/catalina/localhost/ 文件夹下新建一个xml文件，名字可以自己定义。 person.xml

2. 在这个文件里面写入以下内容

   	<?xml version='1.0' encoding='utf-8'?>
   	<Context docBase="D:\xml02"></Context>

3. 在浏览器上面访问

   http://localhost:8080/person/xml的名字即可

###给Eclipse配置Tomcat


1. 在server里面 右键新建一个服务器， 选择到apache分类， 找到对应的tomcat版本， 接着一步一步配置即可。
2. 配置完毕后， 在server 里面， 右键刚才的服务器，然后open  ， 找到上面的Server Location , 选择中间的 Use Tomcat installation...

3. 创建web工程， 在WebContent下定义html文件， 右键工程， run as server
