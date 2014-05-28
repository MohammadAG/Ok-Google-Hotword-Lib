Ok-Google-Hotword-Lib
=====================

Reimplementation of library used by OEMs to include the "Ok Google" hotword in launchers

Usage
=====

Import this library into your IDE and include it in your project. (Eclipse: right click, properties, Android, Library -> Add)
In your launcher's main Activity:

In onCreate, create a HotwordServiceClient instance.

````
mHotwordServiceClient = new HotwordServiceClient(this);
````

In onAttachedToWindow:
````
mHotwordServiceClient.onAttachedToWindow();
mHotwordServiceClient.requestHotwordDetection(true);
````

In onDetachedFromWindow:
````
mHotwordServiceClient.onDetachedFromWindow();
mHotwordServiceClient.requestHotwordDetection(false);
````

In onResume:
````
mHotwordServiceClient.requestHotwordDetection(true);
````

In onPause:
````
mHotwordServiceClient.requestHotwordDetection(false);
````

You're done, the mic in the Google Search widget should now be filled.
