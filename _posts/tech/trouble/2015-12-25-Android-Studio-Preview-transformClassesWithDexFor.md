---
layout: post
title: Android Studio 2.0 Preview4 transformClassesWithDexFor
category: 问题与修复
tags: Android Studio 2.0,Instant Run
description: 最近做一个项目用了很多开源的组建，项目有可能会发布，所以提前整理整理各个开源协议，有助于项目发展
---
### Android Studio 2.0 已经出来一段时间了，昨天下载体验了一下，想体验一下传说中的秒编译。结果遇到了编译错误
```
Error:Execution failed for task ':mobile:transformClassesWithDexForDebug'.
> com.android.build.api.transform.TransformException: com.android.ide.common.process.ProcessException: org.gradle.process.internal.ExecException: Process 'command 'C:\Program Files\Java\jdk1.7.0_79\bin\java.exe'' finished with non-zero exit value 3

```
由于资料少只在谷歌上搜到很少信息，在StackOverFlow和一篇[博客][1]上看到很少的信息，都尝试过了总之就是没有效果，最后在这里发现了解决方案[感谢谷歌][2]
添加下面信息
```
dexOptions {
    javaMaxHeapSize "4g"
}

```
可能是我8G内存的黑苹果太渣了
体验了一下很不错的，以后不用蛋疼的等待了

  [1]: http://blog.mosil.biz/2015/11/android-instant-run/
  [2]: https://code.google.com/p/android/issues/detail?id=195138
