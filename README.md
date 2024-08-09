# UMShareWeChat
基于有盟分享, 依赖完整版微信SDK(带微信支付功能),快速导入直接使用

解决微信和有盟中同时出现微信sdk错误.
解决有盟sdk中微信无支付功能
解决最新有盟sdk中,不能唤出微信分享页面

原UMCShare组件中，完整版的微信SDK不包含支付功能, 为了解决这个问题,且保证微信sdk能正常更新情况下,直接依赖了微信sdk

pod UMShareWeChat 
将会自动依赖有盟中 UMCommon、 UMDevice、UMShare/UI、UMAPM、UMCCommonLog等sdk
自动依赖 WechatOpenSDK
