# Check List

> Please read all the items listed here and check if they have met the requirements. Otherwise, the traffic will be blocked, and fill rate is not high, and revenue would be low. Please check carefully.

## 1. Client UA and IP Address Reporting

**Please make sure `Client UA` 和 `Client IP address` will send through `http header` when you send a request to ZPLAY Ads**

> If the client UA or IP is not passed through the header, the server's IP will be taken as the client address, and ZPLAY Ads platform will block the excessive IP as the cheating traffic.

## 2. Parameter Verify

- If the request from iOS device, please be sure to pass the device's `IDFA`, otherwise there will be no ad fill

- If the request from Android device, please be sure to pass at least one of parameter in `IMEI` `AdvertisingID` `AndroidID` `MAC`, otherwise no ad fill

- Please make sure the app_id, app_name, app_cat, ad_unit_id, unit_type in request are same with the corresponding values that you have registered on [ZPLAY Ads Platform](https://wwww.zplayads.com) in advance.

## 3. Using WebView to Load ZPLAY Ads HTML on Android device

a. allow WebView to execute Javascript

```java
mWebView.getSettings().setJavaScriptEnabled(true);
```

b. adding Javascript interface

```java
mWebView.addJavascriptInterface(new ZPLAYAdsJavascriptInterface(), "ZPLAYAds");
```

class ZPLAYAdsJavascriptInterface.java code as following:

```java
private class ZPLAYAdsJavascriptInterface {

        @JavascriptInterface
        public void onCloseSelected() {
            // This method will be called when user close the playable ad, you can handle ad close event in this method
        }

        @JavascriptInterface
        public void onInstallSelected() {
            // This method will be called when user click "download" button, you can handle app install event in this method
        }
    }
```

c. respond install event of WebView

- `ZPLAYAdsJavascriptInterface.onInstallSelected()` method will be invoked when ad is clicked, please jump to App Store in this method.

d. respond close event of WebView

- `ZPLAYAdsJavascriptInterface.onCloseSelected()` method will be invoked when ad is closed，please close the WebView in this method.

## 4. Using WKWebView to Load ZPLAY Ads HTML on iOS device

a. Add `zplayads` script message handle in WKWebView

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

b. Listening to `WKScriptMessageHandler` delegate method

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

c. Listen to Click Event and Open Application Market

- `user_did_tap_install` method will be invoked when ad is clicked, please open built-in App Store in `handlePlayablePageMessage:()`.

- [CLICK HERE](AppStore) to see code sample how to open built-in AppStore.

d. listen to Close Event and execute

- `close_playable_ads` method will be invoked when ad is closed, please close the WKWebView in `handlePlayablePageMessage:`
