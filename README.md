![logo](https://github.com/user-attachments/assets/0d41b803-968a-41a8-809a-0dd3d91ec489)

## 1. Add the SDK as a dependency 

```sh
$ flutter pub add trackmyuser_sdk
```

## 2. Initialise the SDK

```dart
TrackmyuserKey key = TrackmyuserKey();
key.setAndroidKey("YOUR_ANDROID_SDK_KEY");
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

## 4. Deeplinks

Navigate to the [Magiclinks page](https://dashboard.trackmyuser.com/magiclinks) in the dashboard. Click on "Setup Deeplink" to add support for deeplinks for both the Android and iOS versions of your app.

# 1. Android setup 

Select the android version of your app from the dropdown and add your APK's SHA256 fingerprint. Make sure to add the fingerprints of all your build (debug/release) variants.

<img width="590" alt="image" src="https://github.com/user-attachments/assets/311efd2b-06d6-4cd9-b4ba-baf526fcf71d" />

# 2. iOS setup

Select the iOS version of your app from the dropdown and add your app's team Id.

<img width="590" alt="image" src="https://github.com/user-attachments/assets/e883dff0-230e-4858-ad15-7b1fe134bc8b" />

# 3. SDK setup

```dart
TrackmyuserConfig config = TrackmyuserConfig(key);
config.deferredDeeplinkCallback = (Map<String, String> params){
  String deeplinkValue = params["dlv"] ?? "";
  String deeplinkValueSub1 = params["dlv_sub1"] ?? "";
};
TrackmyuserSdk.init(config);
```

## 5. User Tracking

The user Id will be automatically be attached to all events fired in the session. The user Id can also be used in the S2S API to attribute installs to events. 

```dart
TrackMyUserSDK.setUserId(userId: "USER_ID")
```
