<img src="https://bluemixassets.eu-gb.mybluemix.net/api/Products/image/logos/conversation.svg?key=[starter-watson-conversation]&event=readme-image-view" alt="Watson Conversation Logo" width="200px"/>

## Conversation
IBM Cloud Mobile Foundation Starter for Conversation in Swift

[![](https://img.shields.io/badge/bluemix-powered-blue.svg)](https://bluemix.net)
[![Platform](https://img.shields.io/badge/platform-ios_swift-lightgrey.svg?style=flat)](https://developer.apple.com/swift/)

### Table of Contents
* [Summary](#summary)
* [Requirements](#requirements)
* [Configuration](#configuration)
* [Run](#run)
* [License](#license)

### Summary
This IBM Cloud Mobile Starter showcases the Mobile Foundation and Conversation service from Watson and provides integration points for each of the IBM Cloud Mobile services.

### Requirements
* iOS 8.0+
* Xcode 8
* Swift 3.0

### Configuration
* [IBM Cloud Mobile services Dependency Mangagement](#bluemix-mobile-services-dependency-management)
* [Watson Dependency Management](#watson-dependency-management)
* [Mobile Foundation Configuration](#mobile-foundation-configuration)
* [Watson Credential Mangement](#watson-credential-management)

#### IBM Cloud Mobile services Dependency Management
The IBM Cloud Mobile services SDK uses [CocoaPods](https://cocoapods.org/) to manage and configure dependencies. To use our latest SDKs you need version 1.1.0.rc.2.

You can install CocoaPods using the following command:

```bash
$ sudo gem install cocoapods --pre
```

If the CocoaPods repository is not configured, run the following command:

```bash
$ pod setup
```

For this starter, a pre-configured `Podfile` has been included in the **ios_swift/Podfile** location. To download and install the required dependencies, run the following command from the **ios_swift** directory:

```bash
$ pod install
```
Now open the Xcode workspace: `{APP_Name}.xcworkspace`. From now on, open the `.xcworkspace` file because it contains all the dependencies and configurations.

If you run into any issues during the pod install, it is recommended to run a pod update by using the following commands:

```bash
$ pod update
$ pod install
```

> [View configuration](#configuration)

#### Mobile Foundation Configuration

Follow the steps below to configure the Mobile Foundation service
##### Steps:

* Go to the project folder and find the shell scripts by name **mfpregisterapp.sh** and **mfpstartersetup.sh**. Ensure that you have *execute* and *write* permissions to run these scripts.
* Run **mfpstartersetup.sh**.
* Run **mfpstartersetup.sh**. This should set up the Mobile Foundation prereqs for running the starter
* Update **mfpclient.plist**: Replace the **host** value with **mobilefoundationUrl** value from **BMSCredentials.plist**. Keep the other things as default.


> [View configuration](#configuration)

#### Watson Credential Management
After the dependencies are built and configured for the IBM Cloud Mobile service SDKs as well as the Watson Developer Cloud SDK, configure the Watson Conversation service. A Watson Conversation service on IBM Cloud has already been created for you, find it under your list of services.

You need to create or upload a conversation file to your Watson Conversation service on IBM Cloud to allow proper interaction with the service.

In the Conversation service instance dashboard on IBM Cloud launch the Conversation tooling dashboard by clicking the **Launch tool** button:

![ConversationDashboard](README_Images/ConversationDashboard.png)

Now create your own Conversation Workspace or upload the sample we have included in this project (**bluemix_mobile_qa_workspace.json**):

![ConversationWorkspace](README_Images/ConversationWorkspace.png)

After you have created or uploaded a Conversation Workspace you need to get the Workspace Id. Click the **View details** list item to see the Workspace information. Save the **WorkspaceID** which is to be included in the application configuration:

![ConversationWorkspaceID](README_Images/ConversationWorkspaceID.png)

Navigate to **ViewController.swift** and replace the String `"YOUR_WORKSPACE_ID"` (approx. line ~198) with your Watson Conversation workspace id saved earlier. The placeholder is found in the `ViewController` class, `invokeMFPAdapter()` function.

The other unique credentials from your Watson Conversation service are already injected into the application, so no further configuration is required.

> [View configuration](#configuration)

### Run
You can now run the application on a simulator or physical device:

<img src="README_Images/ConversationScreenshot.png" alt="Conversation App Screenshot" width="250px"/>

The Watson Conversation service allows you to add a natural language interface to your application to automate interactions with your end users. This application shows an application of this service that allows you to have a conversation with Watson. Watson sends an initial conversation, which you can then reply to and continue the interaction with the service.

### License
This package contains code licensed under the Apache License, Version 2.0 (the "License"). You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0 and may also view the License in the LICENSE file within this package.
