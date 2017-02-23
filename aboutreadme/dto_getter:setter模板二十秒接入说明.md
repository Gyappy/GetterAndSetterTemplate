# GetterAndSetterTemplate
  to complete DTO by automation to prevent from npe, unnecessary object and so on
  (调研时一些同事建议去掉setter模板，接口DTO对setter的使用很少，考虑到一些本地JavaBean的场景可能使用到，所以也提供出来按需配置)
###意义
  * 调研的时候发现一些团队的开发不太注意成员变量的访问权限,这样需要在业务逻辑代码中加入很多保护性代码,用这种模板+注解的方式可以把这些保护性代码收敛到DTO中。
  * 在字段数量较多的情况一个DTO粗略估算平均耗时3~5分钟，机械性的操作也容易出错(比如用复制粘贴的方式拷贝函数然后改函数名和返回的变量名，忘记改就会返回不该返回的变量,极大增加调试成本)。
  * 一些好的代码风格和编程习惯比如在创建新对象的时候赋值保存避免下次重复创建这样的小case，可以固化到模板中。
### 规范 应该注意DTO内的成员变量的访问权限,除了特殊情况应该定位private,避免破坏对象的封装性。推荐的方式是这样:
  ![Image](https://github.com/Gyappy/GetterAndSetterTemplate/blob/master/aboutreadme/x1.png)
### AS提供一套默认模板生成成员变量的getter/setter方法
  右键-->Generate-->Getter/Setter/Getter and Setter
  
  ![Mou icon](https://github.com/Gyappy/GetterAndSetterTemplate/blob/master/aboutreadme/x2.png)
  ![Mou icon](https://github.com/Gyappy/GetterAndSetterTemplate/blob/master/aboutreadme/x3.png)
### 新模板接入方式
  点击getter and setter-->如题所示不知怎么描述-->把模板源码帖到编辑框内-->使用时把模板指定成对应模板即可
  
  ![Mou icon](https://github.com/Gyappy/GetterAndSetterTemplate/blob/master/aboutreadme/x4.png)
  ![Mou icon](https://github.com/Gyappy/GetterAndSetterTemplate/blob/master/aboutreadme/x5.png)
  
### 一些要点
  * 对于getter和setter可以自主选择模板
  * 对于实现list,map接口的对象,默认实例化成ArrayList和HashMap,如有其它需要比如LinkedList之类,得手动改一下
  
### 大致效果展示
  * before:
  
  ![Mou icon](https://github.com/Gyappy/GetterAndSetterTemplate/blob/master/aboutreadme/x6.png)
  ![Mou icon](https://github.com/Gyappy/GetterAndSetterTemplate/blob/master/aboutreadme/x7.png)
  * after:
  
  ![Mou icon](https://github.com/Gyappy/GetterAndSetterTemplate/blob/master/aboutreadme/x8.png)
  ![Mou icon](https://github.com/Gyappy/GetterAndSetterTemplate/blob/master/aboutreadme/x9.png)
###后续优化计划
  * 把json解析和模板相结合成一条龙服务。
###一个相对典型的使用场景。比如这种比较keng的情况
  ![Mou icon](https://github.com/Gyappy/GetterAndSetterTemplate/blob/master/aboutreadme/x10.png)
  
  1秒钟以后变成这样,太长截不下，有150行，用默认模板+手写的话,每个6分钟拿不下来，还有可能写错!：
  ![Mou icon](https://github.com/Gyappy/GetterAndSetterTemplate/blob/master/aboutreadme/x11.png)
