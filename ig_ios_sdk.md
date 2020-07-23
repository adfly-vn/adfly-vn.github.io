
# Interactive Game


## Steps

1. Apply appKey and appSecret
2. Download and intergated [SDK](sdk/ig/XBInterActiveAdSDK.framework.zip)


## XBInterActiveAdSDK.framework Usage

### Import
 * import XBInterActiveAdSDK

### Init
* appkey: String
* appSecret: String

``` swift 
XBInterActiveAdManager.shared.start(appKey: appKey, appSecret: appSecret, complete: { (error) in
            if error == nil {
                print("init success")
            }
        })

```
  
#### Params
* scale:  default is 1， size: (100, 100)
* origin: defalut distance is  0.1 * custom.bounds.height  to customView bottom
* customView: the superView of adView
* onShowAction: on icon show call
* onClickAction: on click icon call
* onCloseAction: on close icon call

``` swift
 XBInterActiveAdManager.shared.showAd(scale: 1, origin: CGPoint.zero, customView: self.view, onShowAction: {
            print("Show FloatIcon")
        }, onClickAction: {
            print("User clicked")
        }, onCloseAction: {
            print("User closed")
        })

```
