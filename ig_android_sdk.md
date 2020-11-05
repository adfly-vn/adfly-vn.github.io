
# Interactive Game

> The document is outdated. Please see the [new doc](https://doc.adfly.vn/docs/android/)!  
> The document is outdated. Please see the [new doc](https://doc.adfly.vn/docs/android/)!  
> The document is outdated. Please see the [new doc](https://doc.adfly.vn/docs/android/)!  


## Steps

1. Apply appKey and appSecret
2. Download and intergated [SDK](sdk/ig/xbinteractivelibrary-release.aar)


## Usage

There are two api. It's recommended to call Init api when app is start.
And call showAd when you want show floatIcon.

### Dependencies

Add follow dependencies in `build.gradle`
```
    implementation 'androidx.appcompat:appcompat:1.1.0'
    implementation 'androidx.constraintlayout:constraintlayout:1.1.3'
    testImplementation 'junit:junit:4.12'
    androidTestImplementation 'androidx.test.ext:junit:1.1.1'
    androidTestImplementation 'androidx.test.espresso:espresso-core:3.2.0'

    implementation 'com.zhy:okhttputils:2.6.2'
    implementation "com.squareup.okhttp3:okhttp:3.4.1"
    // gson
    implementation 'com.google.code.gson:gson:2.8.5'
    testImplementation 'junit:junit:4.12'

    //fresco
    implementation "com.facebook.fresco:fresco:1.13.0"
    implementation "com.facebook.fresco:animated-gif:1.13.0"
    implementation "com.facebook.fresco:animated-webp:1.13.0"
    implementation "com.facebook.fresco:webpsupport:1.13.0"
    implementation "com.facebook.fresco:imagepipeline:1.13.0"
    implementation "com.facebook.fresco:imagepipeline-okhttp3:1.13.0"
    implementation "com.facebook.fresco:drawee:1.13.0"

    // rxjava
    implementation 'io.reactivex.rxjava2:rxjava:2.x.x'
    implementation 'io.reactivex.rxjava2:rxandroid:2.0.2'

    // chorme tabs
    implementation 'androidx.browser:browser:1.0.0'

    implementation fileTree(dir: 'libs', include: ['*.aar'])
```

### Init
* appkey: String
* appSecret: String
* InitCallback，callback for success or failure

``` java 
XbInteractiveManager.getInstance().init(MainActivity.this, "demo", "ac4a10da9e7f62adb59dbe7f62adb59dbe770e8d",
        new InitCallback() {
            @Override
            public void initSuccess() {
            }

            @Override
            public void initFailure(int failCode, String msg) {
            }
        });

```
  
#### showAd

Config layout


``` xml

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">
    <RelativeLayout android:id="@+id/linearlayout"
        android:layout_width="match_parent"
        android:layout_height="match_parent">
        <com.xb.interactivelibrary.InteractiveAdView
            android:id="@+id/tnteractive"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="20dp"/>
    </RelativeLayout>
</androidx.constraintlayout.widget.ConstraintLayout>

```

Call api

``` java
InteractiveAdView interactive = findViewById(R.id.tnteractive);
interactive.showAd();  
// interactive.showAd(width, height);   Show ad with custom width and height
```
