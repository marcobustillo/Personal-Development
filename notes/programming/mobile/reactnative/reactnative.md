# React Native

## Getting Started
There are two ways to create a project in react native. You can use `create-react-native-app app_name` which is the easiest way to start a react native app. And the `react-native-cli` which builds native code in your project.
Personally I would choose to start using the `react-native-cli` immediately as it is scalable. You can create small, medium, large apps without the worry of ejecting its config file.

## Installation
- First you need node and npm. I assume you have node and npm installed. if not go to it's main website at https://nodejs.org/en/download/
- Install `react-native-cli` using npm -install -g react-native-cli. the -g tag is important there because we need it to be called globally
- Install Android studio Choose a "Custom" setup when prompted to select an installation type. Make sure the boxes next to all of the following are checked:
   - Android SDK
   - Android SDK Platform
   - Performance (Intel ® HAXM)
   - Android Virtual Device
- Install the Android SDK
Android Studio installs the latest Android SDK by default. Building a React Native app with native code, however, requires the Android 8.0 (Oreo) SDK in particular. Additional Android SDKs can be installed through the SDK Manager in Android Studio.

The SDK Manager can be accessed from the "Welcome to Android Studio" screen. Click on "Configure", then select "SDK Manager".

## Common Issues/Errors
- [Issue] SDK location not found. Define location with sdk.dir in the local.properties file or with an ANDROID_HOME environment variable.
  - [Solution] Create local.properties file in android/ folder and paste this line `sdk.dir = C:\\Users\\USERNAME\\AppData\\Local\\Android\\sdk` then re-run
- [Issue] "@babel/runtime/helpers/builtin/interopRequireDefault"
  - [Solution] npm add @babel/runtime
