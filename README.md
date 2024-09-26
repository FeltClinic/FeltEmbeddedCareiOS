# Felt Embedded Care iOS SDK
Felt offers a seamless telehealth experience inside health apps. Our platform handles the full user lifecycle, including onboarding, payments, and doctor visits - with just a few lines of code.

## Getting Started

Add this package to your Xcode project by selecting `File` > `Add Package Dependency` and entering the repository URL:

```
https://github.com/FeltClinic/felt-embedded-care-ios
```

At app launch, initialize the SDK with your SDK key using [`EmbeddedCare.shared.initialize`](https://feltclinic.github.io/felt-embedded-care-ios/documentation/feltembeddedcare/embeddedcare/initialize(sdkkey:)). For example with UIKit, the implementation would look like:

```diff
+ import FeltEmbeddedCare

class AppDelegate: UIApplicationDelegate {
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {

        // other initialization logic

+        do {
+            try EmbeddedCare.shared.initalize(sdkKey: /* your Felt SDK Key */)
+        } catch {
+            // Error will be thrown for invalid key
+        }

    }
}
```

Now you can embed care experiences in a variety of ways, below are a few examples. 
See [Presenting Care](https://feltclinic.github.io/felt-embedded-care-ios/documentation/feltembeddedcare/documentation#Component-Experiences) for other approaches.

```swift

// for a modal care experiences
EmbeddedCare.shared.presentExperience(.splashScreen)

// for components to be shown in your existing views
let componentView = ComponentView(experience: .dismissableCallToAction, metadata: [:])
self.view.addSubview(componentView)

```

Finally, you will need to share context with the SDK to have a complete experience. This can be achieved by

* setting user metadata with [`setUserDetails()`](https://feltclinic.github.io/felt-embedded-care-ios/documentation/feltembeddedcare/embeddedcare/setuserdetails(userid:email:metadata:)) 
* setting component metadata with [`ComponentView(..., metadata: )`](https://feltclinic.github.io/felt-embedded-care-ios/documentation/feltembeddedcare/componentview/init(experience:metadata:))

That's it! By working with Felt, we will populate these views with a customized, white-labeled experience that will delight your users.

## Documentation
You can find reference documentation and user guides [here](https://feltclinic.github.io/felt-embedded-care-ios/documentation/feltembeddedcare/documentation).

## Support

### Slack
We should have a Slack Connect setup you should be able to find us individually below or at `#<company name>-felt`

Reach out to sid (at) feltclinic.com or josh (at) feltclinic.com if you are not finding us on Slack.


### Email

* sid (at) feltclinic.com
* daniel (at) feltclinic.com
