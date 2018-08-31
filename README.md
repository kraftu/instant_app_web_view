# Android Instant Apps - Error accessing resources in features after use WebView

## How to repeat error
An error is reproduced: Any device

```
1) Install instant App, open feature 'buy';
2) On the GoodbyeActivity activity, click NextActivity;
```

## Crash log
Device: Samsung SM-G920F Android 7.0
```
08-31 16:09:48.666 12323-12497/? E/Isotope: UID: [10418]  PID: [12323] IActivityManagerProxy : Instant app: com.google.android.instantapps.samples.hellofeature crashed: java.lang.RuntimeException: Unable to start activity ComponentInfo{com.google.android.instantapps.samples.hellofeature/com.instantappsamples.feature.bye.NextActivity}: android.content.res.Resources$NotFoundException: Resource ID #0x7e020001
        at android.app.ActivityThread.performLaunchActivity(ActivityThread.java:2927)
        at android.app.ActivityThread.handleLaunchActivity(ActivityThread.java:2988)
        at android.app.ActivityThread.-wrap14(ActivityThread.java)
        at android.app.ActivityThread$H.handleMessage(ActivityThread.java:1631)
        at android.os.Handler.dispatchMessage(Handler.java:102)
        at android.os.Looper.loop(Looper.java:154)
        at android.app.ActivityThread.main(ActivityThread.java:6682)
        at java.lang.reflect.Method.invoke(Native Method)
        at com.android.internal.os.ZygoteInit$MethodAndArgsCaller.run(ZygoteInit.java:1520)
        at com.android.internal.os.ZygoteInit.main(ZygoteInit.java:1410)
     Caused by: android.content.res.Resources$NotFoundException: Resource ID #0x7e020001
        at android.content.res.ResourcesImpl.getValue(ResourcesImpl.java:202)
        at android.content.res.Resources.loadXmlResourceParser(Resources.java:2968)
        at android.content.res.Resources.getLayout(Resources.java:1984)
        at android.view.LayoutInflater.inflate(LayoutInflater.java:425)
        at android.view.LayoutInflater.inflate(LayoutInflater.java:378)
        at com.android.internal.policy.PhoneWindow.setContentView(PhoneWindow.java:446)
        at android.app.Activity.setContentView(Activity.java:2544)
        at com.instantappsamples.feature.bye.NextActivity.onCreate(NextActivity.java:11)
        at android.app.Activity.performCreate(Activity.java:6942)
        at android.app.Instrumentation.callActivityOnCreate(Instrumentation.java:1126)
        at android.app.ActivityThread.performLaunchActivity(ActivityThread.java:2880)
        at android.app.ActivityThread.handleLaunchActivity(ActivityThread.java:2988) 
        at android.app.ActivityThread.-wrap14(ActivityThread.java) 
        at android.app.ActivityThread$H.handleMessage(ActivityThread.java:1631) 
        at android.os.Handler.dispatchMessage(Handler.java:102) 
        at android.os.Looper.loop(Looper.java:154) 
        at android.app.ActivityThread.main(ActivityThread.java:6682) 
        at java.lang.reflect.Method.invoke(Native Method) 
        at com.android.internal.os.ZygoteInit$MethodAndArgsCaller.run(ZygoteInit.java:1520) 
        at com.android.internal.os.ZygoteInit.main(ZygoteInit.java:1410) 
```

The code is taken from: https://github.com/googlesamples/android-instant-apps
```
This sample introduces feature modules to the Hello World sample.

Code and resources that are only required within a single feature module
can be found in the corresponding feature modules.

* `features/base` -> Shared
* `features/hello` -> Hello feature
* `features/bye` -> Bye feature
```
