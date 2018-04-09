# 持续更新ing ...
## iOS

### 类和对象
1. [iOS 程序 main 函数之前发生了什么](http://blog.sunnyxx.com/2014/08/30/objc-pre-main/)
2. [谈ObjC对象的两段构造模式](http://blog.devtang.com/2013/01/13/two-stage-creation-on-cocoa/)
3. [从 NSObject 的初始化了解 isa](http://draveness.me/isa/)
4. [深入解析 ObjC 中方法的结构](http://draveness.me/method-struct/)
5. [深入理解 Objective-C : Category](http://tech.meituan.com/DiveIntoCategory.html)

### MRC和RAC
1. [Objective-C 中的内存分配](https://hit-alibaba.github.io/interview/iOS/ObjC-Basic/MM.html)

### UIKit
1. [UIApplication 深入学习](http://www.cocoachina.com/ios/20121023/4958.html)
2. [详解 CALayer 和 UIView 的区别和联系](https://www.jianshu.com/p/079e5cf0f014)
3. [UIViewController 生命周期](https://hit-alibaba.github.io/interview/iOS/Cocoa-Touch/UIViewController.html)

### 像素绘制
1. [绘制像素到屏幕上](https://objccn.io/issue-3-1/)

### 事件处理
1. [Cocoa Touch 事件处理流程--响应者链](http://www.cnblogs.com/snake-hand/p/3178070.html)
2. [iOS 中的事件处理、响应者链条以及第一响应者](http://www.cnblogs.com/forwk/p/4843159.html)
3. [在 Target-Action 中使用响应链](http://swift.gg/2016/01/06/utilize-the-responder-chain-for-target-action/)

### GCD
1. [GCD 深入理解：第一部分](https://github.com/nixzhu/dev-blog/blob/master/2014-04-19-grand-central-dispatch-in-depth-part-1.md)
2. [GCD 深入理解：第二部分](https://github.com/nixzhu/dev-blog/blob/master/2014-05-14-grand-central-dispatch-in-depth-part-2.md)
3. [GCD](https://bestswifter.com/deep-gcd/)

### Runtime
1. [深入理解 Objective-C ：方法缓存](http://tech.meituan.com/DiveIntoMethodCache.html)
2. [理解 Objective-C Runtime](http://blog.cocoabit.com/yi-li-jie-objctive-c-runtime/)
3. [Objective-C Runtime 1 小时入门教程](https://www.ianisme.com/ios/2019.html)
4. [Method Swizzling 和 AOP 实践](http://tech.glowing.com/cn/method-swizzling-aop/)
5. [刨根问底：对于 self = [super init] 的思考](https://www.jianshu.com/p/9b36e1b636d8)

```
// 冒泡排序 进行n-1趟, 每趟都进行相邻数字比较
void bubbleSort (int arr[], int len)
{
    int temp;
    for (int i = 0; i < len - 1; i++) {
        bool flag = true;
        for (int j = 0; j < len - 1 - i; j++) {
            if (arr[j] > arr[j + 1]) {
                flag = false;
                temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
        if (flag) {
            break;
        }
    }
}

// 选择排序 外部循环进行len-1趟, 每趟找出最小的元素放到该趟的首位, 第i趟的时候从i+1一直到len-1进行比较
void selectionSort (int arr[], int len)
{
    
    
    int temp, min;
    for (int i = 0; i < len - 1; i++) {
        min = i;
        for (int j = i + 1; j < len; j++) {
            if (arr[min] > arr[j]) {
                min = j;
            }
        }
        if (min != i) {
            temp = arr[min];
            arr[min] = arr[i];
            arr[i] = temp;
        }
    }
}

// 插入排序 每一步都是将待排序的序列插入到前面已经排好序的序列中
void insertSort (int arr[], int len)
{
    for (int i = 0; i < len; i++) {
        int j = i;
        int temp;
        while (j > 0 && arr[j] < arr[j - 1]) {
            temp = arr[j];
            arr[j] = arr[j - 1];
            arr[j - 1] = temp;
            j--;
        }
    }
}

// 快速排序
void quickSort (int arr[], int l, int r)
{
    if (l < r) {
        int i = l, j = r, x = arr[l];
        while (i < j) {
            while (i < j && arr[j] >= x) {
                j--;
            }
            if (i < j) {
                arr[i++] = arr[j];
            }
            while (i < j && arr[i] < x) {
                i++;
            }
            if (i < j) {
                arr[j--] = arr[i];
            }
        }
        arr[i] = x;
        quickSort(arr, l, i - 1);
        quickSort(arr, i + 1, r);
    }
}




### Runloop
1. [深入理解 RunLoop](http://blog.ibireme.com/2015/05/18/runloop/)

### 锁
1. [Objective-C 中不同方式实现锁(一)](http://www.tanhao.me/pieces/616.html/)
2. [Objective-C 中不同方式实现锁(二)](http://www.tanhao.me/pieces/643.html/)
3. [iOS 中的锁](http://blog.duicode.com/1286.html)
4. [iOS 开发－多线程开发之线程安全篇](http://www.cnblogs.com/GarveyCalvin/p/4212611.html)
5. [iOS 多线程-各种线程锁的简单介绍](https://www.jianshu.com/p/35dd92bcfe8c)
6. [关于 @synchronized，这儿比你想知道的还要多](http://yulingtianxia.com/blog/2015/11/01/More-than-you-want-to-know-about-synchronized/)
7. [iOS 中保证线程安全的几种方式与性能对比](https://www.jianshu.com/p/938d68ed832c)

### 动画 图层
1. [Core Animation](https://hit-alibaba.github.io/interview/iOS/Cocoa-Touch/Animation.html)
2.	[CoreGraphics教程](http://www.cnblogs.com/xdream86/archive/2012/12/12/2814552.html)  
3.	画板实现 

	[涂鸦画板](https://www.jianshu.com/p/b7213a14b471)
 
	[你画我猜](https://www.jianshu.com/p/bcd864c5dece)

### 并发编程
1. [Cocoa 并发编程](https://hit-alibaba.github.io/interview/iOS/Cocoa-Touch/Multithreading.html)
2. [iOS 多线程编程 —— GCD 与 NSOperation 总结](https://bestswifter.com/multithreadconclusion/)

### 设计模式
1. [设计模式](https://hit-alibaba.github.io/interview/iOS/Cocoa-Touch/Design.html)

### NSNotification
1. [深入NSNotification（iOS）](https://www.jianshu.com/p/3f453e41ae11)

### Block
1. [iOS中__block 关键字的底层实现原理](https://www.jianshu.com/p/404ff9d3cd42)

### KVC KVO
1. [Objective-C中的KVC和KVO](http://yulingtianxia.com/blog/2014/05/12/objective-czhong-de-kvche-kvo/)
2. [KVO安全使用(防止dealloc中移除监听者崩溃)](https://www.jianshu.com/p/f8bb89aad2df)

### 面试
1. [三月份实习校招后，也该为 BAT 秋招囤一些干货了](http://ios.jobbole.com/84506/)
2. [笔试面试知识整理](https://hit-alibaba.github.io/interview/)
3. [招聘一个靠谱的iOS — 参考答案](https://github.com/ChenYilong/iOSInterviewQuestions)
4. [丁香园面试总结](http://blog.csdn.net/wang631106979/article/details/73525528#%E7%AE%80%E5%8D%95%E8%AE%B2%E8%A7%A3%E4%B8%80%E4%B8%8Bhttp%E8%AF%B7%E6%B1%82%E4%BB%A5%E5%8F%8Aget-post%E7%9A%84%E5%8C%BA%E5%88%AB)
5. [iOS算法面试](http://blog.csdn.net/yangshebing21/article/details/51292477)

### 经典第三方框架原理分析
1. 音频视频处理(各种编码的转码)[OpenELGS学习教程](https://www.jianshu.com/u/815d10a4bdce)
2. 图层动画的处理(关于CoreAniamtion, CoreGraphics框架的学习)
3. 异步渲染复杂视图框架[AsyncDisplayKit](https://github.com/facebookarchive/AsyncDisplayKit)
4. OpenGL学习网站[Learning OpenGl](https://learnopengl-cn.github.io/)
5. [CoreImage框架学习](https://www.objccn.io/issue-21-6/)
6. [Componentkit](https://componentkit.org/docs/component-api.html)
7. [初识CK框架](https://cloud.tencent.com/developer/article/1006394)
8. [Object-C++编译(C++和OC混编的叫法, 可以相互调用, 因为C++和OC对象都是指针形式存在的)](http://www.cocoachina.com/bbs/read.php?tid-9111.html)
9. [源码分析系列(Alamofire, SDWebImage, Masonry, BlocksKit, MBProgressHUD)](https://github.com/Draveness/analyze)

### Swift经典框架
1. [RxSwift](https://github.com/ReactiveX/RxSwift) 函数式编程
2. [Alamofire](https://github.com/Alamofire/Alamofire)网络请求库
3. [ObjectMapper](https://github.com/Hearst-DD/ObjectMapper) JSON转换Model框架
4. [Kingfisher](https://github.com/onevcat/Kingfisher)图片加载
5. [SnapKit](https://github.com/SnapKit/SnapKit)约束布局

## vue

#### 技术栈
1. [vue.js](https://cn.vuejs.org/v2/guide/)
2. [vue-router](https://router.vuejs.org/zh-cn/index.html)
3. [vue-strap](https://github.com/yuche/vue-strap)
4. [webpack](http://webpack.github.io/)

## Git

[git github gitlab](https://www.jianshu.com/p/8d497989f704)

### 书籍记录
1. The Swift Programming Language 3.0 swift编程语言3.0
2. iOS Core Animation: Advanced Techniques CoreAnimation高级技术
3. iOS应用逆向工程第二版(小黄书)
4. Effective OC 52个有效的方法
5. iOS高级编程(内存, block, GCD)
6. 图解HTTP
7. 图解TCP/IP

```

