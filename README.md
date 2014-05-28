Ok-Google-Hotword-Lib
=====================

Reimplementation of library used by OEMs to include the "Ok Google" hotword in launchers

Usage
=====

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
