# 试验maven

有3个模块```mod1```、```mod2```和```mod-out```，均依赖了```commons-lang:commons-lang```  
依赖关系为：  
```
mod-out
|--mod1
   |--commons-lang:2.1
|--mod2
   |--commons-lang:2.3
|--commons-lang:2.5
```
在```mod-out```中指定```dependencyManagement```
```
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>commons-lang</groupId>
            <artifactId>commons-lang</artifactId>
            <version>2.6</version>
        </dependency>
    </dependencies>
</dependencyManagement>
```
最终结果为在打出的zip包中，```mod-out```依赖```commons-lang```版本为2.6  
即传递依赖的版本也可以被管理起来