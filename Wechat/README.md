# 微信相关开发Tips

## 公众号二维码

知道一个微信公众号,怎么知道它的二维码是什么呢? - 知乎 - 知乎
2016年1月21日 - 

http://open.weixin.qq.com/qr/code/?username=

「=」之后键入公众号的「微信号」,就可以得到公众号的二维码图片。 发布于 2016-01-21 7 条评论 感谢 ...

## 公众号关注页

找一条历史素材，获取参数__biz：

https://mp.weixin.qq.com/mp/profile_ext?action=home&__biz=MzAxMzU2NTE5MA==#wechat_redirect

## 隐藏/显示微信中网页右上角按钮

公众号在有需要时（如不需要用户分享某个页面），可在网页中通过JavaScript代码隐藏网页右上角按钮。

https://mp.weixin.qq.com/wiki/11/b8e9756b6f56f285661d82d843aa9b4f.html

```javascript
// 接口调用代码（JavaScript）

function onBridgeReady(){
 WeixinJSBridge.call('hideOptionMenu');
}

if (typeof WeixinJSBridge == "undefined"){
    if( document.addEventListener ){
        document.addEventListener('WeixinJSBridgeReady', onBridgeReady, false);
    }else if (document.attachEvent){
        document.attachEvent('WeixinJSBridgeReady', onBridgeReady); 
        document.attachEvent('onWeixinJSBridgeReady', onBridgeReady);
    }
}else{
    onBridgeReady();
}
// 返回说明
// 隐藏底部导航栏没有返回值。（需要显示请把hideOptionMenu换成showOptionMenu）
```
