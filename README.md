---
description: >-
  Video verification Gesture is based on the video liveliness check which is
  confirmed by the user performing some face gestures in real-time. This also
  records the video and save it for reference.
---

# Video Verification IOS Framework

### Integration For IOS(Swift)

#### Permission required in App-level Plist file

The app is based on the video which the user shoots, so permission required for the process is camera and document storage.

1. NSCameraUsageDescription
2. NSDocumentsFolderUsageDescription

{% code title="Parentapp-info.plist" %}
```markup
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	.
	.
	.
	.
	<key>NSCameraUsageDescription</key>
	<string>Needs Camera permission</string>
	<key>NSLocationUsageDescription</key>
	<string>Needs Location Permission </string>
	<key>NSDocumentsFolderUsageDescription</key>
	<string>Need to save video</string>
</dict>
</plist>
```
{% endcode %}

### Calling framework

1. Add framework in the parent application.

![add files to workspace and add in target setting.](<.gitbook/assets/Screenshot 2021-02-11 at 12.57.26 PM.png>)



&#x20; 2\. ViewController part to open SDK

{% code title="CallerVC.swift" %}
```swift
//...
//...
// Add framework in the module import
import VVFramework


class ViewController: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()
               
        // Do any additional setup after loading the view.
    }

 @IBAction func openSdk(_ sender: Any) {

// VVFramework has a public shared instance, having function launchVideoVerification
    VVFramework.sharedInstance.launchVideoVerification(
//parameters: sessionId
    sessionId: sessionIdInput,
//caller: UIViewController
    caller: self, 
//success handler: block of function to execute on success
    successHandler: {
                    print("Sucessfully completed Video Verification")
                    
                },
// failure handler: block of function which has 2 parameter 
//err: as String and errortype as type of error categorized
    failHandler: {err,errortype in
                    switch errortype{
                        
                    case .camera: //camera related error
                        break
                    case .network: //network related error
                        break
                    case .apiFailure: // api failed 
                        break
                    case .integration: //Session id or caller not configured or invalid
                        break
                    }
                    print(err)
                    print(errortype)
                    self.presentErrorAlert(message: err)
                    
                })

}
    
    

}
```
{% endcode %}

