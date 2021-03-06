<p align="center">
  <img src="artwork/header.png">
</p>

*Note: This version of Pulse is not available on the App Store. Apple rejected it because "the overall concept is not suited for the App Store", despite my numerous attempts to appeal, call, and point out apps that did the exact same thing as Pulse. If you know someone at Apple that could help with this situation, it would be most appreciated.*

# Pulse SMS - iOS Client

This is a [Pulse SMS](https://messenger.klinkerapps.com/overview) client for iOS. This is **not** a replacement SMS app for your iPhone.

**This iOS app is simply a client to the Pulse backend service.** It doesn't replace iMessage on your iPhone, and it doesn't allow you to text through the phone number associated with your iPhone. It acts like the Pulse web client would, or a tablet using Pulse. 

Pulse is a service that I built for Android. It is meant to allow you to use your personal phone number, when sending text messages from your computer, tablet, watch, tv, or any other device. As a backend service, it is really just a forwarding utility, based around Firebase Cloud Messaging. Since Android has exposed APIs to build a replacement SMS app, Pulse works as a normal SMS app on your phone, then any other device you are using use FCM to communicate directly and instantly with the Android phone app, through Pulse's REST APIs. Similarly, when messages are received to the phone, it will POST those message to the backend to get distributed to your other devices.

Pulse is not a typical client-server application, since the phone is the controller and root of all the communication, but the backend and Android app handles that gracefully and solves that issue for you. As a client app, you really only need to worry about the exposed APIs.

Typical use-cases for this iOS client:

* Having an iPad and an Android phone and wanting to be able to use Pulse to text on the iPad
* Having a separate work iPhone that you want to be able to use with your personal Android phone number
* Demonstration of the APIs, their usage, and implementation for other third party clients

The app is not available on the Apple App Store, Apple has rejected it because "the overall concept of the app is not suited for the App Store". Since there are specific configurations to be made with Apple's APN push notification system, push notifications for new messages will not be able to come to a self-built version of the app. They will only be possible if Apple accepts the app to their App Store.

## Building the App

Open the `Pulse.xcworkspace` in XCode to build and edit the project. You will need a developer license to build to a real device. You can build the app to the simulator if a device isn't available. The simulator will not have have push notification support for new messages, but it will have real-time updates through FCM.

### Dependency Management

I use `CocoaPods` for dependency management. The `Pods` directory is checked in to source control, so unless you are adding or changing dependencies, you shouldn't have to worry about the setup here. 

To set up `CocoaPods`:

1. Run `sudo gem install cocoapods` to install `CocoaPods`.
2. Run `pod install` to install new pods to the project.
3. Run `pod update` if you are only updating the version of existing pods.

## Contributing

Please fork this repository and contribute back using [pull requests](https://github.com/klinker24/messenger-ios/pulls). Features can be requested using issues on our Pulse platform issue tracker, rather than creating issues directly on this repo: https://github.com/klinker-apps/messenger-issues.

## Changelog

The full changelog for the iOS app can be found [here](CHANGELOG.md).

## License

    Copyright 2018 Luke Klinker

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
