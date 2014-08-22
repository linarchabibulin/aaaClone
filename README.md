## 1. General Info

The use of AdformTracking SDK requires the following:

* Xcode 5.0 or later.
* iOS SDK 7.0 or later.
* Requires deployment target 6.0 or later

## 2. Drag AdformTracking SDK folder to your project.

* Download latest build version of AdformTracking SDK.
* Drag AdformTrackingSDK folder to your project, when asked select **Copy items into destination group's folder**.

* Go to your application target’s configuration > General > Linked Frameworks and Libraries section and add these frameworks to your project:
   * **AdSupport.framework**

* Go to your application target’s configuration > Build settings > Linking > Other Linker Flags, and set **-ObjC** flag.


* Go to your application target’s scheme > Edit Scheme > Build, and add AdformTrackingSDK target at top.

* Import **AdformTrackingSDK.h** in AppDelegate:
    
		#import “AdformTrackingSDK/AdformTrackingSDK.h”

## 3. Starting AdformTrackingSDK

In `application:didFinishLaunchingWithOptions:` method create track point, add parameters (optional) and call `startTrackingWithTrackPoint:` method with created trackPoint:

			TrackPoint *trackPoint = [[TrackPoint alloc] initWithTrackingPointId:@"trackPoint"];
    		[trackPoint setCustomParameter:@"parameterValue" withKey:@"parameterKey"];
    		[trackPoint setCustomParameter:@"parameterValue2" withKey:@"parameterKey2"];
    		[[AdformTrackingSDK sharedInstance] startTrackingWithTrackPoint:trackPoint]; 

## 4. Sending information to server manually

* Import **AdformTrackingSDK.h**:
    
		#import “AdformTrackingSDK/AdformTrackingSDK.h”

* Create tracking point, set parameters (optional) call `sendTrackingInformation:` method:

		TrackPoint *trackPoint = [[TrackPoint alloc] initWithTrackingPointId:@"trackPoint"];
		// set parameters here
	 	[[AdformTrackingSDK sharedInstance] sendTrackingInformation:trackPoint];
	

## 5. Setting track point parameters

* Set application name:
	
		[trackPoint setDefaultApplicationName:@"demoApp"];

* Set section name:
	
		[trackPoint setSectionName:@"demoAppSection"];

* Set single custom parameter:
	
		[trackPoint setCustomParameter:@"customParam" withKey:@"CustomKey"];

	Parameter and its key must be NSString variable.

* Set dictionary filled with custom parameters:
	
		[trackPoint setCustomParameters:parametersDictionary];
