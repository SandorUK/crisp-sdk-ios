![Crisp](https://raw.githubusercontent.com/crisp-im/crisp-sdk-ios/master/docs/img/logo_blue.png)

Chat with app users, integrate your favorite tools, and deliver a great customer experience.

# Crisp iOS SDK

![Crisp screenshot](https://raw.githubusercontent.com/crisp-im/crisp-sdk-ios/master/docs/img/crisp_screenshot.jpg)

[![CocoaPods](https://img.shields.io/cocoapods/v/Crisp.svg)](https://cocoapods.org/?q=crisp)
[![Carthage Compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)
[![Twitter](https://img.shields.io/badge/twitter-@crisp_im-blue.svg?style=flat)](http://twitter.com/crisp_im)


## Installation

### Cocoapods

[CocoaPods](http://cocoapods.org) is a dependency manager for Cocoa projects. You can install it with the following command:

```bash
$ gem install cocoapods
```

To integrate Crisp into your Xcode project using CocoaPods, specify it in your Podfile:

```ruby
source 'https://github.com/CocoaPods/Specs.git'
platform :ios, '9.0'
use_frameworks!

target '<Your Target Name>' do
    pod 'Crisp'
end
```

Then, run the following command:

```bash
$ pod install
```

### Carthage

[Carthage](https://github.com/Carthage/Carthage) is a decentralized dependency manager that builds your dependencies and provides you with binary frameworks.

You can install Carthage with [Homebrew](http://brew.sh/) using the following command:

```bash
$ brew update
$ brew install carthage
```

To integrate Crisp into your Xcode project using Carthage, specify it in your `Cartfile`:

```ogdl
github "crisp-im/crisp-sdk-ios"
```

Run `carthage update` to build the framework and drag the built `Crisp.framework` into your Xcode project.


## Requirements

⚠️ Adding Camera and Photo permissions is mandatory, `NSCameraUsageDescription` and `NSPhotoLibraryUsageDescription` in  `Info.plist`, to inform your users that you need to access to the Camera and Photo Library. You also have to enable **"iCloud Documents"** capability

## Usage

Start using Crisp by adding the following code on your AppDelegate :

```Swift
import Crisp
Crisp.initialize(websiteId: "YOUR_WEBSITE_ID")
```

### Chatbox

You can add the Crisp bubble by adding in your view `CrispButton()` :

```Swift
import UIKit
import Crisp

class ViewController: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()
        let crispButton = CrispButton()
        view.addSubview(crispButton)
        crispButton.bottomAnchor.constraint(equalTo: view.bottomAnchor, constant: -20).isActive = true
        crispButton.rightAnchor.constraint(equalTo: view.rightAnchor, constant: -20).isActive = true
    }

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
    }
}

```

### Preferences

You can change the main Crisp's color and texts :

#### Color

```swift
Crisp.preference.setColor(.red)
Crisp.preference.setColor(def: .blue)
Crisp.preference.setColor(hex: "000000")
```

Enum `ThemeColors` :

- blue
- amber
- black
- blueGrey
- blueLight
- brown
- cyan
- green
- greenLight
- grey
- indigo
- orange
- orangeDeep
- pink
- purple
- purpleDeep
- red
- teal

#### Theme Text

```Swift
Crisp.preference.setThemeText(.defaultChat)
Crisp.preference.setThemeText(string: "LOCALIZED_STRING")
```

Enum `ThemeText` :

- defaultChat
- oneChat
- twoChat
- threeChat
- fourChat

#### Theme Welcome

```Swift
Crisp.preference.setThemeWelcome(.defaultChat)
Crisp.preference.setThemeWelcome(string: "LOCALIZED_STRING")
```

Enum `ThemeWelcome` :

- defaultChat
- oneChat
- twoChat
- threeChat
- fourChat
- fiveChat

### User

- Setters

``` Swift
Crisp.user.set(email: "quentin@crisp.im")
Crisp.user.set(avatar: "http://your.website.com/user_id/size")
Crisp.user.set(nickname: "Quentin de Quelen")
Crisp.user.set(phone: "+33645XXXXXX")
```

- Getters

```Swift
let email = Crisp.user.email
let avatar = Crisp.user.avatar
let nickname = Crisp.user.nickname
let phone = Crisp.user.phone
```

### Chatbox

Open the chatbox with :

```Swift
Crisp.chat.open()
```

Close the chatbox with :

```Swift
Crisp.chat.close()
```

## More

You can also check out our [API Reference](https://crisp-im.github.io/crisp-sdk-ios/) for more detailed information about our this SDK.

## Credits

Crisp iOS SDk is owned and maintained by [Crisp IM, inc](https://crisp.chat/en/). You can chat with us on [crisp](https://crisp.chat) or follow us on Twitter at [Crisp_im](http://twitter.com/crisp_im)

## License

Crisp iOS SDk is under Copyright license. see [LICENSE](https://raw.githubusercontent.com/crisp-im/crisp-sdk-ios/master/LICENSE) for more details.
