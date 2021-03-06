![Platform](https://img.shields.io/cocoapods/p/QuantiBase.svg)
![Swift 5](https://img.shields.io/badge/Swift-5-orange.svg)
[![travis badge](https://travis-ci.org/Qase/base-ios.svg?branch=master)](https://travis-ci.org/Qase/base-ios)
[![codebeat badge](https://codebeat.co/badges/14d7c0b8-7dce-4d5a-a0fa-37a3fb047351)](https://codebeat.co/projects/github-com-qase-base-ios-master)
[![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)
[![Pod compatible](https://cocoapod-badges.herokuapp.com/v/QuantiBase/badge.png)](https://cocoapods.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Maintainer: troupmar](https://img.shields.io/badge/Maintainer-troupmar-blue.svg)](mailto:martin.troup@quanti.cz)
[![Qase: base-ios](https://img.shields.io/badge/Qase-base_ios-ff69b4.svg)](https://github.com/Qase/base-ios)

## QuantiBase

Base-ios repository consists of useful extensions, general classes and protocols that we gather and use while working on our projects. The main goal is to create a central point of such snippets that can be reused across various projects. We constantly review and enrich the repository aiming to reach maximum reusability. We take full advantage of functional programming with reactive layer. For that purpose we use external libraries and thus QuantiBase will require following: 
- **Overture** (https://github.com/pointfreeco/swift-overture)   
  A library providing helpful generic functions that enhance functional programming approach. 
- **RxSwift** (https://github.com/ReactiveX/RxSwift)  
A library providing reactive layer that enables to enhance reactive programming approach.
- **Action** (https://github.com/RxSwiftCommunity/Action)  
A library used with RxSwift to provide an abstraction on top of observables: actions.
- **RxDataSources** (https://github.com/RxSwiftCommunity/RxDataSources)  
A library used with RxSwift to provide reactive API for table and collection views.
    


## Features
- **Services**:
    - AppLifecycleService: providing app lifecycle callbacks (such as “didFinishLaunchingNotification”) via reactive observables instead of using global notifications
    - KeyboardService: providing keyboard callbacks (such as “keyboardWillShow”) via reactive observables instead of using global notifications
    - ReachabilityService: providing reachability status (such as “ReachableViaWiFi”) via reactive observables
    - BluetoothService: wrapper around CoreBluetooth’s CBPeripheralManager providing its callbacks via reactive observables
- **JSONParser**: our own implementation of JSON parsing & serialization
- **HTTPNetworking**: our own reactive implementation of REST network communication that fully supports our JSONParser
- **UserDefaultsStorable protocol**: used to group models that support UserDefaults storing 
- **ViewModelBindable protocol**: used by classes and structs that bind viewModels (useful for MVVM architecture)
- **BinaryCodable protocol**: used to group models that support Binary encoding & decoding
- **Queue**: implementation of queue using array
- **TableModel class**: used when creating table views aiming to encapsulate the data structure of the table (will be soon obsolete since it is mostly replaced by RxDataSources external library)
- **MultipleDelegating protocol**: extending the highly used Delegate pattern that supports multiple delegates (will be soon obsolete since it is mostly replaces by reactive observables)
- 3rd party:
    - **LoremSwiftum**: helpful class providing random strings of variable length
    - **Overture operators**:
    operators on top of existing functions introduced in Overture library
        - `|>` for `with`
        - `^` for get and `prop`
        - `<>` for `concat`
        - `>>>` and `<<<` for `pipe`
        - `>=>` for `chain`
- Useful subclasses of UIViewController & UIView
- Binary extensions for basic data types
- Other useful extensions for basic data types, reactive types and UIKit classes
- Other

## Installation
### Carthage

[Carthage](https://github.com/Carthage/Carthage) is a decentralized dependency manager that builds your dependencies and provides you with binary frameworks. You can install Carthage with [Homebrew](https://brew.sh) using the following command:
```
$ brew update
$ brew install carthage
```
To integrate QuantiLogger into your Xcode project using Carthage, specify it in your `Cartfile`:
```
github "Qase/base-ios" ~> 0.0.2
``` 
Run `carthage update` to build the framework and drag the built `QuantiBase.framework` and its dependencies into your Xcode project.

### CocoaPods

[CocoaPods](https://cocoapods.org) is a dependency manager for Cocoa projects. You can install it with the following command:
```
$ gem install cocoapods
```
To integrate QuantiLogger into your Xcode project using CocoaPods, specify it in your Podfile:
```
source 'https://github.com/CocoaPods/Specs.git'
platform :ios, '10.0'
use_frameworks!

target '<Your Target Name>' do
  pod 'QuantiBase', '~> 0.0.2'
end
```

or for macOS

```
source 'https://github.com/CocoaPods/Specs.git'
platform :osx, '10.13'
use_frameworks!

target '<Your Target Name>' do
  pod 'QuantiBase', '~> 0.0.2'
end
```
Then, run the following command:
```
$ pod install
```

### Swift Package Manager
The [Swift Package Manager](https://swift.org/package-manager/) is a tool for managing the distribution of Swift code. The Package Manager is included in Swift 3.0 and above.

It doesn't support iOS, macOS, tvOS or watchOS projects. It only compiles for host platforms (macOS/linux). It is useful for commanline apps. To create a commandline app using SPM please read [this great RayWenderlich article](https://www.raywenderlich.com/750-an-introduction-to-the-swift-package-manager).
In file `Package.swift` in the dependencies parameter add the following: 

`.package(url: "https://github.com/Qase/Base-ios", from: "0.0.2)`

so it should look something like this: 
```
let package = Package(
    name: "YOUR_APP_NAME",
    dependencies: [
        .package(url: "https://github.com/Qase/Base-ios", from: "0.0.2"),
    ]
)
```
then run 
`$ swift build`
and 
`$ 
swift package generate-xcodeproj`

For updating use
`$ swift package update`


## Future development

Code base is still under active development and it is going to grow steadily. You can send requests for other usefull snippets, that can be integrated into library.

## License
[MIT](https://github.com/nishanths/license/blob/master/LICENSE)
