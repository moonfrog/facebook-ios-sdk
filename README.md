# Facebook SDK for iOS

[![Platforms](https://img.shields.io/cocoapods/p/FBSDKCoreKit.svg)](https://cocoapods.org/pods/FBSDKCoreKit)
[![Build Status](https://travis-ci.org/facebook/facebook-ios-sdk.svg?branch=master)](https://travis-ci.org/facebook/facebook-ios-sdk)

[![CocoaPods](https://img.shields.io/cocoapods/v/FBSDKCoreKit.svg)](https://cocoapods.org/pods/FBSDKCoreKit)
[![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)

This open-source library allows you to integrate Facebook into your iOS app.

Learn more about the provided samples, documentation, integrating the SDK into your app, accessing source code, and more
at https://developers.facebook.com/docs/ios

NOTE: By default, the Facebook SDK for iOS is installed in ~/Documents/FacebookSDK

## TRY IT OUT

### Swift Package Manager (available Xcode 11.2 and forward)

1. In Xcode, select File > Swift Packages > Add Package Dependency.
2. Follow the prompts using the URL for this repository and a minimum semantic version of v5.10.0
3. Check-out the tutorials available online at: <https://developers.facebook.com/docs/ios/getting-started>
4. Start coding! Visit <https://developers.facebook.com/docs/ios> for tutorials and reference documentation.

**Note:**

If you explicitly **DO NOT** want to include Swift, import `FBSDKCoreKit` `FBSDKLoginKit` and `FBSDKShareKit`

For projects that include Swift, use `FacebookCore`, `FacebookLogin`, and `FacebookShare`

### CocoaPods

1. If you explicitly **DO NOT** want to include Swift files, add the following to your `Podfile`:

        pod 'FBSDKCoreKit'
        pod 'FBSDKLoginKit'
        pod 'FBSDKShareKit'

   If you would like to use versions of the pods that include Swift, add the following to your `Podfile`:

        pod 'FBSDKCoreKit/Swift'
        pod 'FBSDKLoginKit/Swift'
        pod 'FBSDKShareKit/Swift'

2. Test your install by adding `import FBSDKCoreKit` to your `AppDelegate`
3. Check-out the tutorials available online at: <https://developers.facebook.com/docs/ios/getting-started>
4. Start coding! Visit <https://developers.facebook.com/docs/ios> for tutorials and reference documentation.

## FEATURES

- Login - <https://developers.facebook.com/docs/facebook-login>
- Sharing - <https://developers.facebook.com/docs/sharing>
- App Links - <https://developers.facebook.com/docs/applinks>
- Graph API - <https://developers.facebook.com/docs/ios/graph>
- Analytics - <https://developers.facebook.com/docs/analytics>

## GIVE FEEDBACK

Please report bugs or issues to our designated developer support team -- <https://developers.facebook.com/support/bugs/> -- as this will help us resolve them more quickly.

You can also visit our [Facebook Developer Community Forum](https://developers.facebook.com/community/),
join the [Facebook Developers Group on Facebook](https://www.facebook.com/groups/fbdevelopers/),
ask questions on [Stack Overflow](http://facebook.stackoverflow.com),
or open an issue in this repository.

## LICENSE

See the [LICENSE](LICENSE) file.

## Security Policy

See the [SECURITY POLICY](SECURITY.md) for more info on our bug bounty program.

## DEVELOPER TERMS

- By enabling Facebook integrations, including through this SDK, you can share information with Facebook, including
  information about people’s use of your app. Facebook will use information received in accordance with our
  [Data Use Policy](https://www.facebook.com/about/privacy/), including to provide you with insights about the
  effectiveness of your ads and the use of your app. These integrations also enable us and our partners to serve ads on
  and off Facebook.
- You may limit your sharing of information with us by updating the Insights control in the developer tool
  `https://developers.facebook.com/apps/{app_id}/settings/advanced`.
- If you use a Facebook integration, including to share information with us, you agree and confirm that you have
  provided appropriate and sufficiently prominent notice to and obtained the appropriate consent from your users
  regarding such collection, use, and disclosure (including, at a minimum, through your privacy policy). You further
  agree that you will not share information with us about children under the age of 13.
- You agree to comply with all applicable laws and regulations and also agree to our Terms
  <https://www.facebook.com/policies/>, including our Platform Policies <https://developers.facebook.com/policy/>.and
  Advertising Guidelines, as applicable <https://www.facebook.com/ad_guidelines.php>.

By using the Facebook SDK for iOS you agree to these terms.

## Additional Edit by Amit

## Follow the steps mentioned below for building FB SDK for TPG
The code changes are only in FBSDKLoginKit. But to make the sdk following 3 SDKs are needed for TPG:
1. FBSDKCoreKit
2. FBSDKLoginKit
3. FBSDKShareKit

1. To build the SDK open each top level project in XCode(by double clicking on FBSDK<resp>Kit.xcodeproj file) one by one(don't open all at once) and choose the scheme as FBSDK<resp>Kit-Universal from the list of schemes. 
2. Choose target device as **Generic iOS Device**.
3. Clean(cmd+shift+k) and select Archive from Product menu bar.
4. After the build is completed go to the this location to get the framework
   Macintosh HD⁩ ▸ ⁨Users⁩ ▸ ⁨<username>⁩ ▸ ⁨Library⁩ ▸ ⁨Developer⁩ ▸ ⁨Xcode⁩ ▸ ⁨DerivedData⁩ ▸ ⁨FBSDK<resp>Kit-<some-random-string>⁩ ▸ ⁨Build⁩    ▸ ⁨Intermediates.noindex⁩ ▸ ⁨ArchiveIntermediates⁩ ▸ FBSDK<resp>Kit-Universal⁩ ▸ ⁨IntermediateBuildFilesPath⁩ ▸ UninstalledProducts⁩
5. Copy the framework directory to proj.ios folder(frameworks are just like ordinary folders in Apple).
6. Due to header search path issue(and I also didn't get time to fix it), I have commented out this line from all the header files in the all of the framework header folders: ``` #import "FBSDKCoreKitImport.h" ```. If you can fix it then just commit everything or else you also will have to comment this line in all the header files.
7. These steps do not include how to add a static library framework from scratch. These steps are mentioned keeping in mind that the 3 FBSDK frameworks are already added to xcode and we have just need to upgrade them.

Happy building...
