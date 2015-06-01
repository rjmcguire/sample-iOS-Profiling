# iOS
### Scrolling UITableView
A constantly scrolling UITableView. Has different row heights. Has custom cells with recycling, three UILabels in each cell. Objective-C code implementation is compared with the same JavaScript code in NativeScript for iOS. The apps were designed to keep constant 60 FPS.

Projects:
 - _iOS/TNSScriptList_ - Objective-C implementation
 - _iOS/TNSNativeList_ - NativeScript for iOS implementation (without modules)

For the _TNSScriptList_ app you will have to execute `tns platform add ios`, `tns prepare ios` and use the generated Xcode project in `platforms\ios`.

The CPU and GPU samples are taken with the Xcode instruments. Open the Xcode projects go to Product > Profile. The Memory usage is recorded in Xcode with the projects built in Release.

#### TNSScriptList (NativeScript for iOS)
 - Memory: ~13MB and raises to flat at 48MB
 - CPU: 38.4% Foreground, 28.8% Graphics
 - GPU Driver FPS: ~60

#### TNSNativeList (Objective-C)
 - Memory: ~6.4MB
 - CPU Activity: 31.6% Foreground, 28.8% Graphics
 - GPU Driver FPS: ~60

#### Summary

Overall the additional memory consumed is due to the JS heap and the way JavaScript objects retain the native Objective-C objects.

The CPU usage with NativeScript for iOS is about 21% higher than using pure Objective-C.

