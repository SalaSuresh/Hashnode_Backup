---
title: "How to install .aab file in Android device?"
datePublished: Wed Aug 02 2023 05:56:02 GMT+0000 (Coordinated Universal Time)
cuid: clktbeh2z000f09md28tjhkv1
slug: how-to-install-aab-file-in-android-device
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/q8U1YgBaRQk/upload/a11f3ee782cc72141282d6107af8ac87.jpeg
tags: android-app-development, android-development, android, android-apps

---

This article provides the details for installing the Android signed .aab file on an Android device.

**Requirements:**  
\- Java  
\- Keystore file (.jsk or .keystore file)  
\- Download the bundle tool jar file from the below link  
[https://github.com/google/bundletool/releases](https://github.com/google/bundletool/releases)

**Steps to install the .aab file on an Android device:**

1. Copy the .aab and downloaded bundle tool jar file in the same location and open the terminal in the same location.
    
2. Connect the Android testing device to the computer (enable USB debugging in the Android testing device)
    
3. Run the below command to extract the .apks from the aab file.  
    *Note: The below command will generate the .apks file using debug Keystore in Android SDK.*  
    `java -jar "<bundle tool jar file name>.jar" build-apks --connected-device --bundle="app-release.aab" --output="app.apks"`  
    *Note: Below command will generate the .apks file with a signed Keystore.*  
    `java -jar "< bundle tool jar file name >.jar" build-apks --bundle="app-release.aab" --output="app.apks" --ks=<your keystore path> --ks-pass=pass:<your password> --ks-key-alias=<your KeyAlias> --key-pass=pass:<your password>`
    
4. After running the above command successfully, you can see a .apks file in the same location.
    
5. Now run the below command to install the application in the connected android device using the .apks file.  
    `java -jar "< bundle tool jar file name >.jar" install-apks --apks=app.apks`
    

Reference:  
[https://www.browserstack.com/guide/test-aab-file-on-android-device](https://www.browserstack.com/guide/test-aab-file-on-android-device)