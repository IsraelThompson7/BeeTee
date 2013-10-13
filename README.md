#BeeTee

Demo application for bluetooth device scanning using the iOS private framework "BluetoothManager"


## Summarize

Because it is not trivial to use a private iOS framework, I implemented a demo application for the `BluetoothManager.framework` in iOS 7.

Based on the [AppStore guideline §2.5](https://developer.apple.com/appstore/resources/approval/guidelines.html) not to use private (undocumented) functions it is not possible to publish apps with the `BluetoothManager.framework` in the AppStore. Your may need a valid membership of the [iOS Developer Program](https://developer.apple.com/programs/ios/).

It makes sense that this framework does not work in the simulator.



##Settings

* iOS 7 and greater
* iOS 7 compatible device (does not working on the simulator)
* Xcode 5 and greater
* Right placed header files (see Preparations)


##Preparations


* Find the folder, e.g. by terminal
<pre><code>open /Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS7.0.sdk/System/Library/PrivateFrameworks/BluetoothManager.framework</code></pre>
* Extract the Headers.zip archive and add the extracted folder `Headers` which includes `BluetoothManager.h` and `BluetoothDevice.h` in the directory above.
* Restart Xcode

Remarks: The folder can differ: Please take care about your iOS version. 


##The BluetoothManager.framework

####Available Notificaitons
    BluetoothAvailabilityChangedNotification
    BluetoothDeviceDiscoveredNotification
    BluetoothDeviceRemovedNotification
    
    BluetoothPowerChangedNotification
    BluetoothConnectabilityChangedNotification
    BluetoothDeviceUpdatedNotification
    
    BluetoothDiscoveryStateChangedNotification
    BluetoothDeviceDiscoveredNotification
    BluetoothAvailabilityChangedNotification
    
    BluetoothDeviceConnectSuccessNotification
    BluetoothConnectionStatusChangedNotification
    BluetoothDeviceDisconnectSuccessNotification

####Usage
Can be used e.g. 
<pre><code>[[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(bluetoothAvailabilityChanged:) name:@"BluetoothAvailabilityChangedNotification" object:nil];</code></pre>
and 
<pre><code>- (void)bluetoothAvailabilityChanged:(NSNotification *)notification { ... }</code></pre>
 
 
 
 
 
 
 


##Licence
GPL (v3)
