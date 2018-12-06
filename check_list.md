# 对接后检查清单

> 此处列出的所有对接项请自行阅读，并检查是否都已经符合要求，否则广告在投放过程中，将会出现流量被屏蔽，填充不高，收益较低等问题，请仔细核查检验

## 1. 客户端 UA 和 IP 地址上报

**请确认 `客户端UA` 和 `客户端IP地址` 通过 `http header` 在请求 ZPLAY Ads 平台时传递**

> 客户端 UA、IP 如果不通过 header 传过来，将会取服务端的 IP 做为客户端地址, ZPLAY Ads 平台 会将重复过多的 IP 当做作弊流量被屏蔽掉

## 2. 传递参数校验

- iOS 请求中，请务必将设备的`IDFA`传递，否则无广告填充

- Android 请求中，请务必传递`IMEI` `AdvertisingID` `AndroidID` `MAC`中任意一个参数，否则无广告填充

- 请确保请求中的应用 ID、应用名称、应用分类、广告位 ID、广告位类型与注册时填写信息保持一致

## 3. Android 使用 WebView 加载 ZPLAY Ads HTML

a. 允许 WebView 执行 Javascript 代码

```java
mWebView.getSettings().setJavaScriptEnabled(true);
```

b. 添加 Javascript 接口

```java
mWebView.addJavascriptInterface(new ZPLAYAdsJavascriptInterface(), "ZPLAYAds");
```

ZPLAYAdsJavascriptInterface.java 类实现如下

```java
private class ZPLAYAdsJavascriptInterface {

        @JavascriptInterface
        public void onCloseSelected() {
            // 可玩广告点击关闭按钮时，触发该方法，请在此回调中处理广告关闭事务
        }

        @JavascriptInterface
        public void onInstallSelected() {
            // 当点击"安装"按钮时，触发该方法，请在此回调中处理广告下载事务
        }
    }
```

c. Android 响应 WebView 的 install 事件示例

- 点击事件会回调`ZPLAYAdsJavascriptInterface.onInstallSelected()`方法，请在此方法中处理打开应用市场事务。

d. Android 响应 WebView 的 close 事件示例

- 关闭事件会回调`ZPLAYAdsJavascriptInterface.onCloseSelected()`方法，请在此方法中处理关闭事务。

## 4. iOS 使用 WKWebView 加载 ZPLAY Ads HTML

a. WKWebView 添加`zplayads`脚本消息处理程序

```objective-c
- (WKWebView *)previewAdWebView {d
    if (!_previewAdWebView) {
        WKWebViewConfiguration *config = [[WKWebViewConfiguration alloc] init];
        [config.userContentController addScriptMessageHandler:self name:@"zplayads"];
        config.allowsInlineMediaPlayback = YES;
        CGRect frame =
            CGRectMake(0, 0, [UIScreen mainScreen].bounds.size.width, [UIScreen mainScreen].bounds.size.height);
        _previewAdWebView = [[WKWebView alloc] initWithFrame:frame configuration:config];
        _previewAdWebView.scrollView.bounces = NO;
        _previewAdWebView.navigationDelegate = self;
        _previewAdWebView.autoresizingMask = UIViewAutoresizingFlexibleWidth | UIViewAutoresizingFlexibleHeight;

        if (@available(iOS 11.0, *)) {
            [_previewAdWebView.scrollView setContentInsetAdjustmentBehavior:UIScrollViewContentInsetAdjustmentNever];
        }
    }
    return _previewAdWebView;
}
```

b. 监听`WKScriptMessageHandler`的代理方法

```objective-c
#pragma mark - WKScriptMessageHandler
- (void)userContentController:(WKUserContentController *)userContentController
      didReceiveScriptMessage:(WKScriptMessage *)message {
    if ([message.name isEqualToString:@"zplayads"]) {
        [self handlePlayablePageMessage:message.body];
    }
}
// handle message
- (void)handlePlayablePageMessage:(NSString *)msg {
   if ([msg isEqualToString:@"user_did_tap_install"]) {
        NSLog(@"user_did_tap_install");
    }else if ([msg isEqualToString:@"close_playable_ads"]) {
        NSLog(@"close zplayads...");
    }
}
```

c. 安装事件监听及在应用内打开应用市场

- 点击事件会返回`user_did_tap_install`，在`handlePlayablePageMessage:`处理您的跳转逻辑。

- 打开内置 AppStore 代码示例：[点击此处](AppStore)

d. 关闭事件监听及处理

- 关闭事件会返回 `close_playable_ads`，在`handlePlayablePageMessage:`处理您的关闭逻辑。
