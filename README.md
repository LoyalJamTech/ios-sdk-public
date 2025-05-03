# LoyalJamOfferWallSDK

An iOS SDK for integrating the LoyalJam Offer Wall into your iOS applications.

## Requirements

-   iOS 13.0+
-   Xcode 11+
-   Swift 5.0+

## Installation

### CocoaPods

**Important:** Due to recent privacy updates for Xcode/Mac, you need to set **"User Script Sandboxing"** to **"No"** in your project's Build Settings.

To do this:

1.  Select your project in the Project Navigator
2.  Select your target
3.  Go to the "Build Settings" tab
4.  Search for "User Script Sandboxing"
5.  Set the value to "No"

Without this setting, the SDK may not function properly.

LoyalJamOfferWallSDK is available through [CocoaPods](https://cocoapods.org/). To install it, simply add the following line to your Podfile:

```ruby
pod 'LoyalJamOfferWallSDK', '0.5'
```

Then run:

```bash
pod install
```

### Swift Package Manager

Coming soon.

## Usage

### Basic Implementation

Import the SDK in your file:

```swift
import LoyalJamOfferWallSDK
```

Initialize and display the offer wall:

```swift
let loyalJam = LoyalJamOfferWall.Builder()
    .setAppKey("YOUR_APP_KEY")
    .setAppZoneId("YOUR_APP_ZONE_ID")
    .setUserId("USER_ID")
    .build()

loyalJam.open(from: self)

```

### Advanced Configuration

The SDK supports additional parameters for better targeting and analytics:

```swift
let loyalJam = LoyalJamOfferWall.Builder()
    .setAppKey("YOUR_APP_KEY")
    .setAppZoneId("YOUR_APP_ZONE_ID")
    .setUserId("USER_ID")
    .setIdfa("IDFA")
    .setAge(25)
    .setGender(Gender.male)
    .setSource("SOURCE")
    .setSub1("CUSTOM_PARAM_1")
    .setSub2("CUSTOM_PARAM_2")
    .setSub3("CUSTOM_PARAM_3")
    .setSub4("CUSTOM_PARAM_4")
    .setSub5("CUSTOM_PARAM_5")
    .build()

loyalJam.open(from: self)
```

### Parameter Description


## Example

```swift
import UIKit
import LoyalJamOfferWallSDK

class ViewController: UIViewController {
    
    override func viewDidLoad() {
        super.viewDidLoad()
        let loyalJam = LoyalJamOfferWall.Builder()
            .setAppKey("162bacc0167830d5")
            .setAppZoneId("f9c10cbdf958")
            .setUserId("ios337")
            .setIdfa("idfa123")
            .setAge(30)
            .setGender(Gender.male)
            .setSource("exampleSource")
            .setSub1("sub111")
            .setSub2("sub222")
            .setSub3("sub333")
            .setSub4("sub444")
            .setSub5("sub555")
            .build()

        loyalJam.open(from: self)
    }
}
```

## Privacy Requirements

### iOS 14+ Considerations

For iOS 14+, ensure your app includes the proper privacy descriptions in Info.plist for tracking permission:

```xml
<key>NSUserTrackingUsageDescription</key>
<string>This identifier will be used to deliver personalized offers to you.</string>
```
