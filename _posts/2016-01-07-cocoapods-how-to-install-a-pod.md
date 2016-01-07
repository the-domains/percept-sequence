---
inFeed: true
hasPage: true
inNav: false
inLanguage: null
starred: false
keywords: []
description: ''
datePublished: '2016-01-07T23:52:49.240Z'
dateModified: '2016-01-07T23:52:22.863Z'
title: "CocoaPods - How To Install A Pod\_"
author: []
authors: []
publisher:
  name: null
  domain: null
  url: null
  favicon: null
sourcePath: _posts/2016-01-07-cocoapods-how-to-install-a-pod.md
published: true
url: cocoapods-how-to-install-a-pod/index.html
_type: Article

---
# CocoaPods - How To Install A Pod 

Although the previous post before this one was "Smartphones Will Die", as mentioned in that article, it's still going to be a long long time before Apple's iOS or Google's Android will hit the grave. 

Here  is a simple tutorial on how to install pods from CocoaPods, which is something that itself is easy to do but can be confusing if you've never done it before. ![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/c18a0543-249e-49b8-a525-b0c988dd81fb.jpg)

_**Installation**_

Type "sudo gem install cocoapods" into Terminal. This installs the program CocoaPods onto your machine. _You may be prompted for a password, in which case, just enter the password you use to log into your Mac._

_**Usage**_

1. **Access the project: **If you wanted to install stuff to the Xcode project located at Desktop/exampleProject, you type into terminal: "cd Desktop/exampleProject" first, without the quotes. Xcode must be closed. _NB: you can drag the folder onto terminal to get this location all nicely typed out for you, instead of having to type it out manually. _
2. **Install a cocoapods configuration file (Podfile) into your project:** enter "nano podfile" into terminal, without quotes. The nano editor is kinda like TextEdit in a sense.
3. In this file, type in:
  1. _The platform you are building to._ Type "platform :ios, '8.0'" without quotes, which means that you're installing for iOS version 8.0 onwards.
  2. _To add a pod (e.g. AFNetworking):_ on the next line, simply type "pod 'AFNetworking'". That's it. If you want to specify that you wanna use a certain version (_e.g. 2.0_), type "pod 'AFNetworking', '~ 2.0'" without the quotation marks at the start/end. 
  3. To exit nano, you press ctrl+x. It will ask you if you want to save, so press Y, then enter to exit to terminal. 
4. (If you've never used cocoapods before on your computer, type "pod setup" and press enter. )
5. **Lastly, install the project:** back in terminal, type "pod install" and press enter.
6. **You now have to ignore .xcodproj, and instead open the .xcodworkspace file that's created.** This is so that the dependencies are actually properly in the project. This is the file that you will work with from now on. 
7. **Note that most pods are still written in Objective-C.** So you'll need to create what's called a "linking header". Click on File --- New... --- C file. After you type in the name of the file and press continue, a window pops up that says "Would you like to configure an Objective-C bridging header?" click Yes. You can actually then delete the .c and .h files that are created because we just wanted to prompt the header creation.
8. Go to the file ending in "-Bridging-Header.h". You will now need to import the individual files in the Pods project. We will continue to use AFNetworking as an example.
  1. Type this into the "...-Bridging-Header.h" script:   
\#import "AFNetworking.h"