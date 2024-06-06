可以按照以下方式修改你的Kotlin代码，使其支持返回数据给前端：

使用回调函数：

1. 在原生模块方法中接收一个回调函数作为参数。

```
@ReactMethod
fun isCameraOpened(viewTag: Int, callback: Callback) {
  val view = findCameraView(viewTag)
  val res = view.isCameraOpened()
  Log.d(TAG, "获取设备状态:${res}2333")

  // 将数据返回给前端
  callback.invoke(res)
}
```

2. 在JavaScript中调用原生模块方法，并传入一个回调函数作为参数。

```
NativeModules.MyModule.isCameraOpened(viewTag, (res) => {
  // 在这里处理返回的数据
  console.log(res);
});
```

使用Promise：

1. 在原生模块方法中返回一个Promise对象。

```
@ReactMethod
fun isCameraOpened(viewTag: Int, promise: Promise) {
  val view = findCameraView(viewTag)
  val res = view.isCameraOpened()
  Log.d(TAG, "获取设备状态:${res}2333")

  // 将数据返回给前端
  promise.resolve(res)
}
```

2. 在JavaScript中调用原生模块方法，并使用Promise来处理返回的数据。

```
NativeModules.MyModule.isCameraOpened(viewTag).then((res) => {
  // 在这里处理返回的数据
  console.log(res);
}).catch((error) => {
  // 在这里处理错误
  console.error(error);
});
```
