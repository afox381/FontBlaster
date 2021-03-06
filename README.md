# FontBlaster

### Programmatically load custom fonts into your iOS app.

[![CocoaPods](https://img.shields.io/cocoapods/v/FontBlaster.svg)](https://cocoapods.org/pods/FontBlaster)  [![Carthage Compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage) [![SwiftPM Compatible](https://img.shields.io/badge/SwiftPM-Compatible-brightgreen.svg)](https://swift.org/package-manager/) [![CocoaPods](https://img.shields.io/cocoapods/dt/FontBlaster.svg)](https://cocoapods.org/pods/FontBlaster) [![CocoaPods](https://img.shields.io/cocoapods/dm/FontBlaster.svg)](https://cocoapods.org/pods/FontBlaster)
---
## About

Say goodbye to importing custom fonts via property lists as **FontBlaster** automatically imports and loads all fonts in your app's Bundles with one line of code.

## Features
- [x] CocoaPods Support
- [x] Carthage Support
- [x] Swift PM Support
- [x] Automatically imports fonts from `Bundle.main`
- [x] Able to import fonts from remote bundles
- [x] Sample Project
- [x] Documentation at http://sabintsev.com/FontBlaster/

## Installation Instructions

### CocoaPods
For Swift 3.0 support:

```ruby
pod 'FontBlaster'
```

For Swift 2.3 support:

```ruby
pod 'FontBlaster' :git => 'https://github.com/ArtSabintsev/FontBlaster.git', :branch => 'swift2.3'
```

### Carthage
For Swift 3.0 support:

``` swift
github "ArtSabintsev/FontBlaster"
```

For Swift 2.3 support:

```swift
github "ArtSabintsev/FontBlaster" "swift2.3"
```

### Swift Package Manager
``` swift
.Package(url: "https://github.com/ArtSabintsev/FontBlaster.git", majorVersion: 3)
```

### Manual

1. [Download FontBlaster](//github.com/ArtSabintsev/FontBlaster/archive/master.zip).
2. Copy `FontBlaster.swift` into your project.

## Setup

Typically, all fonts are automatically found in `Bundle.main`. Even if you have a custom bundle, it's usually lodged inside of the `mainBundle.` Therefore, to load all the fonts in your application, irrespective of the bundle it's in, simply call:

```Swift
FontBlaster.blast() // Defaults to Bundle.main if no arguments are passed
```

If you are loading from a bundle that isn't found inside your app's `mainBundle`, simply pass a reference to your `Bundle` in the `blast(_:)` method:

```Swift
FontBlaster.blast(bundle:) // Takes one argument of type Bundle, or as mentioned above, defaults to Bundle.main if no arguments are passed
```

If you need a list of all of the loaded fonts, an overloaded version of the `blast(_:)` method has a completion handler that returns just that. Just like the original method, this method takes either a custom `Bundle` or defaults to `Bundle.main` if no argument is passed.

```Swift

// Defaults to Bundle.main as no argument is passed
FontBlaster.blast() { (fonts) in
  print(fonts) // fonts is an array of Strings containing font names
}

// Custom bundle is passed as argument
FontBlaster.blast(bundle:) { (fonts) in
  print(fonts) // fonts is an array of Strings containing font names
}
```

To turn on console debug statements, simply set `debugEnabled() = true` **before** calling either `blast()` method:

```Swift
FontBlaster.debugEnabled = true
FontBlaster.blast()
```

## Sample Project
A Sample iOS project is included in the repo. When you launch the app, all fonts are configured to load custom fonts, but don't actually display them *until* you push the button. After pushing the button, **FontBlaster** imports your fonts and redraws the view.

## Inspiration
This project builds upon an old solution that [Marco Arment](http://twitter.com/marcoarment) proposed and wrote about on his [blog](http://www.marco.org/2012/12/21/ios-dynamic-font-loading).

## Created and maintained by
[Arthur Ariel Sabintsev](http://www.sabintsev.com/)
