# Cordova ScreenPinning plugin

Cordova plugin exposing Android (API 21+) screen pinning APIs.

## Installation

Run the following command inside your project's folder:

```sh
cordova plugin add https://github.com/raimaj/cordova-plugin-screen-pinning.git
```

## Usage

### enterPinnedMode()

- **successCallback:** [Function optional] - success callback



```js
window.plugins.ScreenPinning.enterPinnedMode(successCallback, errorCallback);
```

### exitPinnedMode()

- **successCallback:** [Function optional] - success callback

- **errorCallback:** [Function(error) optional] - error callback, error message string is passed

```js
window.plugins.ScreenPinning.exitPinnedMode(successCallback, errorCallback);
```

## Device owner (Kiosk Mode)

With the normal pinned mode your app's users will have to confirm a dialog asking whether they want to allow your app to be pinned. They can also leave pinned mode easily with a combination of buttons. If instead you need your app to run in a sort of "Kiosk mode" (which the user cannot leave), you first need to set it as th device owner:

In order to set your app as the device owner you need to run this command while your device is plugged via USB debug:

```sh
adb shell dpm set-device-owner <YOUR APP PACKAGE NAME>/me.raimaj.plugin.DefaultDeviceAdminReceiver
```

For example, if your app package is "com.mydomain.myapp", you would run:

```sh
adb shell dpm set-device-owner com.mydomain.myapp/me.raimaj.plugin.DefaultDeviceAdminReceiver
```



