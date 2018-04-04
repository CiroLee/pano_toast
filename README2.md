## xxxx
　　说起前端UI框架，想必大家能说出很多来，比如很火的基于Vue的UI框架就有很多：饿了么团队开发的Element、Mint(移动端)、Vux、Muse、iView等。想到这里，研究krpano的程序员也想打造一个属于krpano的UI框架，虽然这些通过HTML+CSS的知识完全可以做到，或者修改使用成熟的前端UI框架，但是，可但是，我就是想再造个轮子，造轮子虽然没有什么实用意义，但是造轮子的过程确实学习进步的必经之路，所以接下来的balabala~，就是使用krpano的语法，造一个简易的基于krpano的UI库，设计宗旨就是：无序关注代码，拿来就用。  
效果如下：
  ![pic1](https://github.com/CiroLee/lmworks_data/blob/master/save_05.jpg?raw=true)  
  
　　核心文件：**panotoast.xml**,使用时在主文件中引入:  
  ```
  <include url="panotoast.xml" />
  ```
　　panotoast.xml是一个轻便的文字提示的插件。日常使用过程中，往往会遇到一些文字提示框，比如进入一个场景，弹出该场景的名字的简单文字提示，这个功能虽然简单，但是能做到模块化就好了，panotoast做的就是这件事，把文字提示模块化。   
　　一个简单的使用场景，点击一个按钮，弹出一个文字提示，提示的内容可以动态修改，弹窗的位置也是可变的，比如出现在上边、下边等。在panotoast里，实现以上功能，只需要一个函数：  
##### <p align="center" style="color:#F3750F">**create_toast(*html*,*style*,*delaytime*)**</p>   
在onclick事件里写入：   
```
onclick="create_toast('简单提示'，basic|popup,5)"
```
就会创建一个从屏幕上方出现的文字提示。现在来了解一下这个函数的用法。   
　　　**create_toast(*html*,*style*,*delaytime*)**有三个参数：html、style、delaytime；    
- **html： 提示文字(必选)**
- **style：提示框样式(必选)**
- **delaytime：延迟时间，提示框几秒后自动消失，默认为2s(可选)**
   
这里需要注意的是*style*参数，style参数虽然为一个整体，但是由两部分组成，有上边的例子可以知道，两部分由“|”相隔，没错，就像在krpano中使用样式style一样，“|”表示使用了多个style属性，*style*属性是：“颜色”+“出现位置”的顺序构成(顺序不可更改)。这里预设了4种常规颜色、两种特殊颜色和7个位置，六种颜色分别是：   

- basic ===> 基本（黑）
- warn ==> 警告
- success ==> 成功
- error ==> 错误
