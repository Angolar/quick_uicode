# quick_uicode
## 介绍
一个快速自动生成ui代码的编辑器工具，解除繁琐的ui控件查找赋值和事件注册，包括c#和lua两种语言，lua框架基于tolua#(暂未包含进工程)。<br>
配合使用psd2ugui工具 https://github.com/zs9024/quick_psd2ugui ，让做ui更简单。<br>
其中编辑器中列表的序列化使用了第三方开源的序列化工具reorderble-list: https://github.com/rotorz/unity3d-reorderable-list<br>
unity测试版本:5.3.3f1<br>
## 效果
![旋转效果1](https://github.com/zs9024/quick_uicode/blob/master/Screenshots/code.png)<br>
## 使用
由于每个项目的ui系统都不相同，目前只实现了通用的变量声明，查找赋值，事件注册等功能，如需支持自己的ui框架，需自行修改生成脚本的代码。后续可能会添加定制功能
### 界面结构
* 使用过程按从左到右，从上到下的顺序。
* 左半部分用来加载待处理ui，查找和筛选需要的控件。另外单独出来一个gameobject类型的“其他ui对象”，是为了某些情况可以做整体的隐藏显示或克隆操作。
* 右半部分用来生成代码，并且如果选择脚本继承monobehavior，还可以通过按钮挂载脚本到ui上。
* “绑定ui”操作即自动完成在inspector面板拖动控件赋值的操作，所以和“变量赋值”操作二选一即可。
### 操作提示
* “选择待处理ui”处拖入ui面板
* 点击“查找ui控件”按钮，会显示控件列表，点击列表元素可定位到ui的相应节点，通过“+”“-”号分别添加和剔除控件
* “其他ui对象”列表需自行添加
* 注册事件时，可筛选指定的某些类型，未勾选的控件不会生成事件代码
* 如果不想生成脚本可选择复制代码，将查找或事件注册代码拷贝至自己项目
* 可参考demo场景，codepanel.cs，codepanel.lua
