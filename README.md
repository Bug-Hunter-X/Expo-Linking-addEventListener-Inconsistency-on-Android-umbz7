# Expo Linking.addEventListener Inconsistency on Android

This repository demonstrates a bug related to the inconsistent behavior of `Linking.addEventListener` within Expo's `Linking` API on Android devices.  The issue manifests as the event listener failing to register reliably, preventing the application from properly handling deep links.

## Bug Description

The `Linking.addEventListener` function, used to listen for incoming URLs, does not always trigger as expected on various Android devices. This inconsistency makes it challenging to build reliable deep link functionality. The problem appears to be related to Android version fragmentation and potential manufacturer customizations. 

## Steps to Reproduce

1. Clone this repository.
2. Run the project on an Android device (various devices and Android versions are recommended to observe inconsistency).
3. Attempt to open a deep link (as specified in the code). 
4. Observe that the listener sometimes fires and sometimes does not, leading to inconsistent navigation behavior.

## Solution

The provided solution explores implementing a more robust approach. It includes error handling and attempts to use `Linking.getInitialURL` to check for a URL that might have opened the application.