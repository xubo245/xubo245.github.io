错误：

	hadoop@Mcnode1:~/xubo/tools/JNI/jni-maven$ mvn package	
	Error: Could not find or load main class org.codehaus.classworlds.Launcher

错误原因：

在网上找了一下，说是M2_HOME变量引起的。修改方法就是不要出现M2_HOME变量就好。

	#export M2_HOME=/opt/maven/apache-maven-3.3.3
	#export PATH=$PATH:$M2_HOME/bin
	export M2=/opt/maven/apache-maven-3.3.3
	export PATH=$PATH:$M2/bin

source无法生效，需要重新打开终端：

	hadoop@Mcnode1:~$ mvn -version
	Error: Could not find or load main class org.codehaus.classworlds.Launcher
	hadoop@Mcnode1:~$ vi /etc/profile
	hadoop@Mcnode1:~$ source /etc/profile
	hadoop@Mcnode1:~$ mvn -version
	Error: Could not find or load main class org.codehaus.classworlds.Launcher

测试成功：

	Last login: Tue Jun 21 21:49:34 2016 from host-e-162.ustcsz.edu.cn
	hadoop@Mcnode1:~$ mvn -version
	Apache Maven 2.2.1 (rdebian-14)
	Java version: 1.7.0_79
	Java home: /usr/lib/jvm/jdk1.7.0/jre
	Default locale: en_US, platform encoding: UTF-8
	OS name: "linux" version: "3.16.0-30-generic" arch: "amd64" Family: "unix"


参考
【1】 http://isuifengfei.iteye.com/blog/1853022