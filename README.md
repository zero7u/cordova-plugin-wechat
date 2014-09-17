cordova-plugin-wechat
===============

A cordova plugin, a JS version of Wechat SDK

Feature
===============

Share title, description, image, and link to wechat moment(朋友圈)

Example
===============

See [cordova-plugin-wechat-example](https://github.com/xu-li/cordova-plugin-wechat-example)

Install(iOS)
===============

1. Add [wechat lib](https://open.weixin.qq.com/zh_CN/htmledition/res/dev/download/sdk/iOS_SDK-64.zip) to your project. 

2. ```cordova plugin add https://github.com/zero7u/cordova-plugin-wechat```, or using [plugman](https://npmjs.org/package/plugman), [phonegap](https://npmjs.org/package/phonegap)

3. ```cordova build ios``` (it will fail if you haven't include the wechat lib yet.)

4. Open ```config.xml``` in xcode at the root.

5. Add ```<preference name="wechatappid" value="YOUR_WECHAT_APP_ID" />```

Install(android)
===============

1. Add [wechat li](https://open.weixin.qq.com/zh_CN/htmledition/res/dev/download/sdk/Android_SDK.zip) to your project.

2. ```cordova plugin add https://github.com/zero7u/cordova-plugin-wechat```, or using [plugman](https://npmjs.org/package/plugman), [phonegap](https://npmjs.org/package/phonegap)

3. ```cordova build android``` (it will fail if you haven't include the wechat lib yet.)

4. Add ```<preference name="wechatappid" value="YOUR_WECHAT_APP_ID" />``` to ```config.xml```

5. Add ```<activity android:name=".wxapi.WXEntryActivity" android:label="@string/app_name" android:exported="true" android:theme="@android:style/Theme.Translucent" />``` to your Manirfest file. 

6. Create package ```wxapi``` under your package, and copy ```WXEntryActivity.java``` into it, then correct the package name of your own.

Usage
===============

```Javascript
Wechat.share({
    message: {
       title: "Message Title",
       description: "Message Description(optional)",
       mediaTagName: "Media Tag Name(optional)",
       thumb: "http://YOUR_THUMBNAIL_IMAGE",
       media: {
           type: Wechat.Type.WEBPAGE,   // webpage
           webpageUrl: "https://github.com/zero7u/cordova-plugin-wechat"    // webpage
       }
   },
   scene: Wechat.Scene.TIMELINE   // share to Timeline
}, function (message) {
    alert("Success");
}, function (message) {
    alert("Failed: " + message);
});
```


FAQ
===============

Q: "Wechat not installed", even installed

A: Please make sure "wechatappid" is added in ```config.xml``` 


TODO
===============

1. Share to wechat session(聊天) and wechat favorite(收藏)

2. Add other media types, including music etc.

LICENSE
===============

[MIT LICENSE](http://opensource.org/licenses/MIT)
