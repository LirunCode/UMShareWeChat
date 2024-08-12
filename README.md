# UMShareWeChat
### 基于友盟分享, 依赖完整版微信SDK(带支付功能),快速导入直接使用


原UMCShare组件中，完整版的微信SDK不包含支付功能。为解决同时使用分享和微信支付功能, 有以下几种方式:

##### 方式一 (不推荐)
手动导入友盟分享sdk,替换掉其中含微信文件。  
缺点: 如果友盟和微信sdk都有更新,还得在重新下载最新版本进行替换,且项目过多替换慢容易出错,手动导入过于麻烦。

##### 方式二 
```
pod 'UMShare/Social/ReducedWeChat' #含微信精简版(有盟官方已经不更新)
pod 'WechatOpenSDK' #微信完整版
```

缺点: 
1. UMShare/Social/ReducedWeChat(含微信精简版),官方早已经不更新。
2. 如果这里使用 ```UMShare/Social/WeChat #(友盟完整版微信)``` 和 导入的 ```WechatOpenSDK``` 会发生冲突,  单独使用```UMShare/Social/WeChat``` 又不含微信支付功能。
3. 进过测试友盟最新的sdk(6.10.12),能跳转微信,但不能唤出分享界面。(友盟官方看后续是否修复这个问题)

方式二是网上普遍使用的,虽然解决了友盟和微信更新问题,且导入比较简单。但是在友盟最新的sdk(6.10.12)中,分享能跳转到微信,但是并不能唤出分享界面。

##### 方式三 (推荐)
```
pod UMShareWeChat 
```
方式三只抽离了友盟中对于微信的封装文件,对后续友盟和微信更新并没影响。直接pod使用快捷方便,自动集成有盟微信分享(含支付功能)。

```UMShareWeChat``` 将会自动依赖以下友盟基础库和微信sdk
- UMCommon
-  UMDevice
-  UMShare/UI
-  UMAPM
-  UMCCommonLog
-  WechatOpenSDK

 注意这里不需要pod 有盟中 'UMShare/Social/WeChat'
 如果需要QQ、微博等分享功能,直接正常按照友盟文档导入即可 
