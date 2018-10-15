# HT For Web 笔记

## ht.Node

设置3d是否可见`s('3d.visible',true)`、是否编辑`s('3d.editable',true)`、是否可移动`s('3d.movable',true)`、是否可选中`s('3d.selectable',true)`

设置2d是否可见`s('2d.visible',true)`、是否编辑`s('2d.editable',true)`、是否可移动`s('2d.movable',true)`、是否可选中`s('2d.selectable',true)`

### 2D

~~~ js
// 设置可编辑
graphView.setEditable(true)
// 设置可调整大小
graphView.setRectEditableFunc(function(data){
    return data === air11;
});
// 设置智能旋转
graphView.setRotationEditableFunc(function(data){
    return data === air13;
});
~~~

## 矢量

定义：矢量采用JSON格式描述，使用方式和普通的栅格位图一致，通过ht.Default.setImage('hightopo', jsonObject)进行注册， 使用是将相应图片注册名设置到数据模型即可，如node.setImage('hightopo')和node.setIcon('hightopo')等。