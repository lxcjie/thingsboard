# 1，确认环境

```shell
$ java -version
java version "11.0.10" 2021-01-19 LTS
Java(TM) SE Runtime Environment 18.9 (build 11.0.10+8-LTS-162)
Java HotSpot(TM) 64-Bit Server VM 18.9 (build 11.0.10+8-LTS-162, mixed mode)

$ mvn -version
Apache Maven 3.6.3 (cecedd343002696d0abb50b32b541b8a6ba2883f)
Maven home: C:\apache-maven-3.6.3\bin\..
Java version: 11.0.10, vendor: Oracle Corporation, runtime: C:\Program Files\Java\jdk-11.0.10
Default locale: zh_CN, platform encoding: GBK
OS name: "windows 10", version: "10.0", arch: "amd64", family: "windows"

$ node -v
v16.18.0

$ npm -v
8.19.2
```

# 2，下载源代码

```shell
# Based 3.6.2
git clone https://github.com/lxcjie/thingsboard.git
git checkout dev_v3.6.2
```

# 3，编译源代码

```shell
# 设定maven代理
settings.xml
<mirror>  
	<id>nexus-aliyun</id>  
	<mirrorOf>central</mirrorOf>    
	<name>Nexus aliyun</name>  
	<url>https://maven.aliyun.com/repository/public</url>  
</mirror>

$ mvn clean install -DskipTests
```

# 4，安装PostgreSql

```shell
https://get.enterprisedb.com/postgresql/postgresql-16.2-1-windows-x64.exe

Password: asdqwe123

安装完成后，启动pgAdmin，在用户postgres下面创建数据库thingsboard
```

# 5，拷贝SQL，并创建数据库

```shell
# 拷贝
dao\src\main\resources\sql到application\src\main\data\sql

#执行
application\src\main\java\org\thingsboard\server\ThingsboardInstallApplication.java

# 数据库创建完毕
```

# 6，执行thingsboard服务

```shell
#执行
application\src\main\java\org\thingsboard\server\ThingsboardServerApplication.java
```

# 7，登录系统

```shell
http://localhost:8080

User: sysadmin@thingsboard.org
Pass: sysadmin
```

