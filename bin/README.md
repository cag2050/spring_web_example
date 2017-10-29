spring mvc web例子，参考：https://www.tutorialspoint.com/spring/index.htm  
机器翻译版本：http://wiki.jikexueyuan.com/project/spring/

spring mvc 项目运行的流程：  
1. 当项目在服务器上启动时，我们在浏览器上输入http://localhost:8080/项目名/hello，tomcat服务器会根据加载的web.xml，找到url-pattern进行拦截，并交给配置好的名字为HelloWeb的这个DispatcherServlet；  
2. 然后DispatcherServlet根据相应的配置文件HelloWeb-servlet.xml，由于配置了自动扫描context:component-scan，所以自动识别到controller；  
3. 然后spring的HandlerMapping根据@RequestMapping，将url根目录后面的子路径进行匹配，找到HelloController，并交给默认的printHello()方法运行；  
4. 运行结果返回的"hello"被解析为对应视图显示。  

spring mvc 部署到 tomcat 的2种方式(原理一样)：
1. 右键单击项目，使用 Export > WAR File 选项，将 war 文件保存在 Tomcat 的 webapps 文件夹中，启动tomcat（终端命令：sudo sh startup.sh）。
2. 在 eclipse ee 中新建 tomcat server，将项目部署到server里 (推荐此种方式，eclipse修改能同步发布到tomcat)。  
eclipse EE 配置 tomcat：  
eclipse => preferences => server => runtime environments => 选择要配置的服务器 => 指定服务器安装路径 => finish

部署到tomcat的第一种方式，如果war文件名为spring_web_example.war，则访问路径为：http://localhost:8080/spring_web_example/hello  
部署到tomcat的第二种方式，如果项目名为spring_web_example，则访问路径为：http://localhost:8080/spring_web_example/hello