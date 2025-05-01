## 💖 赞助支持 / Sponsor
如果您喜欢这个项目，可以请作者喝杯咖啡 ☕  
| 平台       | 赞助链接                          |
|------------|----------------------------------|
| 爱发电     | [![爱发电](https://img.shields.io/badge/-点击支持-FFDD00?style=flat-square&logo=alipay&logoColor=000)](https://afdian.com/a/mxcos) |
| 支付宝     | [![支付宝](https://img.shields.io/badge/-扫码赞助-00A0E9?style=flat-square&logo=alipay&logoColor=white)](https://sponsor.mxcos.com/assets/images/qrcode/alipay.png) |
| 微信       | [![微信](https://img.shields.io/badge/-扫码赞助-07C160?style=flat-square&logo=wechat&logoColor=white)](https://sponsor.mxcos.com/assets/images/qrcode/wechat.png) |

> 每一份赞助都将用于服务器费用和持续开发。  
> Every contribution helps cover server costs and development.

# 阿里百川SDK

## 接入说明
    仅支持android，暂不支持IOS

## 更新日志
    - 2022.3.31 更新Android百川组件至最新版

## 1. 注册
[阿里百川](https://baichuan.taobao.com/),
注册阿里百川账号，创建应用，申请权限

## 2. 生成安全图片
- 登录阿里百川开发者控制台, 获取V5版安全图片，放入res/drawable/yw_1222.jpg

## 3. 修改文件
修改android目录下AndroidManifest.xml文件，增加内容:
xmlns:tools="http://schemas.android.com/tools"
tools:replace="android:label"

```
    <manifest
        xmlns:tools="http://schemas.android.com/tools">
        <application
            tools:replace="android:label">
    ...
```

## 4. 混淆文件
在android/app/目录下新增proguard-rules.pro文件,
参考[官方说明](https://baichuan.taobao.com/docs/doc.htm?spm=a3c0d.7629140.0.0.45acbe488rAGhC&treeId=129&articleId=118400&docType=1)
内容:

```
    -keepattributes Signature
    -ignorewarnings
    -keep class javax.ws.rs.** { *; }
    -keep class com.alibaba.fastjson.** { *; }
    -dontwarn com.alibaba.fastjson.**
    -keep class sun.misc.Unsafe { *; }
    -dontwarn sun.misc.**
    -keep class com.taobao.** {*;}
    -keep class com.alibaba.** {*;}
    -keep class com.alipay.** {*;}
    -dontwarn com.taobao.**
    -dontwarn com.alibaba.**
    -dontwarn com.alipay.**
    -keep class com.ut.** {*;}
    -dontwarn com.ut.**
    -keep class com.ta.** {*;}
    -dontwarn com.ta.**
    -keep class org.json.** {*;}
    -keep class com.ali.auth.**  {*;}
    -dontwarn com.ali.auth.**
    -keep class com.taobao.securityjni.** {*;}
    -keep class com.taobao.wireless.security.** {*;}
    -keep class com.taobao.dp.**{*;}
    -keep class com.alibaba.wireless.security.**{*;}
    -keep interface mtopsdk.mtop.global.init.IMtopInitTask {*;}
    -keep class * implements mtopsdk.mtop.global.init.IMtopInitTask {*;}
```

<!--发布: flutter packages pub publish --server=https://pub.dartlang.org-->
