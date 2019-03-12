# Android整理
## Activity
1. 说下Activity生命周期 ？
- 参考解答：在正常情况下，Activity的常用生命周期就只有如下7个
  - onCreate()：表示Activity正在被创建，常用来初始化工作，比如调用setContentView加载界面布局资源，初始化Activity所需数据等；
  - onRestart()：表示Activity正在重新启动，一般情况下，当前  Acitivty从不可见重新变为可见时，OnRestart就会被调用；
  - onStart()：表示Activity正在被启动，此时Activity可见但不在前台，还处于后台，无法与用户交互；
  - onResume()：表示Activity获得焦点，此时Activity可见且在前台并开始活动，这是与onStart的区别所在；
  - onPause()：表示Activity正在停止，此时可做一些存储数据、停止动画等工作，但是不能太耗时，因为这会影响到新Activity的显示，onPause必须先执行完，新Activity的onResume才会执行；
  - onStop()：表示Activity即将停止，可以做一些稍微重量级的回收工作，比如注销广播接收器、关闭网络连接等，同样不能太耗时；
  - onDestroy()：表示Activity即将被销毁，这是Activity生命周期中的最后一个回调，常做回收工作、资源释放；
  
- 延伸：从整个生命周期来看，onCreate和onDestroy是配对的，分别标识着Activity的创建和销毁，并且只可能有一次调用；
从Activity是否可见来说，onStart和onStop是配对的，这两个方法可能被调用多次；
从Activity是否在前台来说，onResume和onPause是配对的，这两个方法可能被调用多次；
除了这种区别，在实际使用中没有其他明显区别；  
