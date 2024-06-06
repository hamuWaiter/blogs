1、在移动应用中，没有onClick事件（对于设置了points-event: auto的元素，onClick不生效），需要使用onTouchStart/onTouchEnd代替，据观察，onClick发生在onTouchStart之后，onTouchEnd之前，所以在移动应用开发中，使用onTouchEnd替换onClick事件:

![](C:\Users\ZZW\Desktop\开发部署\React踩坑之旅\img\1.png)
