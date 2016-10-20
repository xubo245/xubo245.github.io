在maven 的settings里面加入：

```
<profiles>
<profile>
    <id>downloadSources</id>
    <properties>
        <downloadSources>true</downloadSources>
        <downloadJavadocs>true</downloadJavadocs>           
    </properties>
</profile>
</profiles>

<activeProfiles>
  <activeProfile>downloadSources</activeProfile>
</activeProfiles>
```

eclipse可以这样配置：

```
Window > Preferences > Maven and checking the "Download Artifact Sources" and "Download Artifact JavaDoc" options
```

具体请看参考【1】


参考
【1】 http://blog.csdn.net/topwqp/article/details/8902863

