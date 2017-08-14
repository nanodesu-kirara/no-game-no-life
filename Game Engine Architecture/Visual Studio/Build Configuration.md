
## 生成配置
生成配置是解决方案内个别项目的预处理器、编译器和链接器的选项集合 

下面给出一些常用设置，这些设置都可以在项目属性设置中找到

### 预处理器设置：
条件编译conditional compilation
```C++
#ifdef _DEBUG
  code
#endif//_DEBUG
```
上段代码只在DEBUG模式下才会执行

同样的可以使用自定义宏(Marco)
```C++
#ifdef CUSTOM
  code
#endif//CUSTOM
```
在生成配置->预处理器中添加宏CUSTOM，才会执行该段代码

如果#define CUSTOM XXX，也是会执行该段代码

但通过前者可以控制在不同的模式下不同的行为

### 编译器设置：
1. 控制编译产生的对象是否包含调试信息

_通常Debug模式下要包含调试信息，而Release模式则应剔除这些信息_

2. 控制内联函数是否展开(/Ob0/Ob1/Ob2)

_通常Debug模式下禁用该优化选项_


### 链接器设置：
- 输出文件类型
- 输出文件名称
- 输出文件路径

宏的本质是命名变量，是一组**变量/值**对

vs根据项目配置提供了全局设置的宏，例如$(ProjectName)

而输出文件名称就可以使用$(ProjectName)

### 典型的生成配置：
多数项目至少有两个生成配置：Debug & Release

一些典型的生成配置有：
- Debug 
- Release 
- Production 
- Tools
