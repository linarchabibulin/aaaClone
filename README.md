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

* Import **AdformTrackingSDK.h**:
    
		#import “AdformTrackingSDK/AdformTrackingSDK.h”

## 3. Starting AdformTrackingSDK

Call method in AppDelegate application:didFinishLaunchingWithOptions: method:

	[[AdformTrackingSDK sharedInstance] startTrackingWithTrackingId:your_developer_id withView:your_main_controller_view]];	 

your_developer_id - Adform provided developer id.<br>
your_main_controller_view - view of a controller, that is always accessible during apps life time.

## 4. Sending information requests manually

* Import **AdformTrackingSDK.h**:
    
		#import “AdformTrackingSDK/AdformTrackingSDK.h”

* Call method with ir without section name parameter:

		[[AdformTrackingSDK sharedInstance] sendTrackingInformation];
	
		[[AdformTrackingSDK sharedInstance] sendTrackingInformation:@"section_name"];
	

## 5. Changing default app name

* Changed app name will be only used when sending information data:
	
	[[AdformTrackingSDK sharedInstance] setDefaultApplicationName:@“app_name"];

