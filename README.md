![logo](https://github.com/user-attachments/assets/0d41b803-968a-41a8-809a-0dd3d91ec489)

## 1. Add the SDK as a dependency 

```sh
$ flutter pub add trackmyuser_sdk
```

## 2. Initialise the SDK

```dart
TrackmyuserKey key = TrackmyuserKey();
key.setAndroidKey("YOUR_ANDROID_SDK_KEY);
key.setiOSKey("YOUR_IOS_SDK_KEY");
TrackmyuserConfig config = TrackmyuserConfig(key);
TrackmyuserSdk.init(config);
```

## 3. Event Tracking

```dart
TrackmyuserEvent event = TrackmyuserEvent("EVENT_CODE");
event.setRevenue("USD", 10);
TrackmyuserSdk.trackEvent(event);
```

## 4. Deferred Deeplink Listener

```dart
TrackmyuserConfig config = TrackmyuserConfig(key);
config.deferredDeeplinkCallback = (Map<String, String> params){
  String deeplinkValue = params["dlv"] ?? "";
  String deeplinkValueSub1 = params["dlv_sub1"] ?? "";
};
TrackmyuserSdk.init(config);
```
