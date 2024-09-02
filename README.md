# Messenger SSL Pinning Bypass

Bypass Messenger SSL pinning on Android devices.  
Supported ABIs: `arm64-v8a`, `x86`  
Latest version: `v391.2.0.20.404`

If you like this project:  
[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/eltimusa4q)  

**Bitcoin**: bc1q6kvvun3cfm5kadesxflntszp8z9lqesra35law  
**Ethereum**: 0x47633Ef59b0F765b7f8047b0A56230cfeBB34027

## Patched APK (No Root)

Download the latest patched APK: 
+ [messenger-v468.0.0.45.109-arm64-v8a.apk](https://github.com/123edi10/Messenger-SSL-Pinning-Bypass/releases/tag/v468.0.0.45.109-arm64-v8a)
+ [messenger-v391.2.0.20.404-arm64-v8a.apk](https://github.com/Eltion/Messenger-SSL-Pinning-Bypass/releases/download/v391.2.0.20.404/messenger-v391.2.0.20.404-arm64-v8a.apk)
+ [messenger-v391.2.0.20.404-armeabi-v7a.apk](https://github.com/Eltion/Messenger-SSL-Pinning-Bypass/releases/download/v391.2.0.20.404/messenger-v391.2.0.20.404-armeabi-v7a.apk)
+ [messenger-v391.2.0.20.404-x86.apk](https://github.com/Eltion/Messenger-SSL-Pinning-Bypass/releases/download/v391.2.0.20.404/messenger-v391.2.0.20.404-x86.apk)

[See all versions](https://github.com/Eltion/Messenger-SSL-Pinning-Bypass/releases/)

## Run using Frida (Requires Root)

This method requires frida-tools and also frida-server running in the device
```
frida -U -l .\messenger-ssl-pinning-bypass.js -f com.facebook.orca
```

## Patch APK

You can create your own patched APK. 


### Requirements Linux (Ubuntu):
1. Install java JRE: `sudo apt install default-jre`
2. Install apksigner: `sudo apt install apksigner`
3. Install zipalign: `sudo apt install zipalign`  

Note: apksigner and zipalign can also be found in android sdk [build-tools](https://dl.google.com/android/repository/build-tools_r30.0.1-linux.zip)

### Requirements Windows:
1. Install java JRE
2. Download [build-tools](https://dl.google.com/android/repository/build-tools_r30.0.1-windows.zip) and unzip
3. Add unzip folder to path variable

### Instructions

1. Download Messenger apk file.
2. Install requirements > `pip install -r requirements.txt`
3. Run script > `python patch_apk.py -i <input apk> -o <output apk>`

After that an patched apk file should be generated.

## Intercept network traffic

You can use a tool like mitmproxy or Burp Suite to intercept the network.

1. Install patched APK in the device
2. Install [mitmproxy](https://mitmproxy.org/) or [Burp Suite](https://portswigger.net/burp)
3. Set up proxy for wifi settings or run: `adb shell settings put global http_proxy <proxy>`

Now you should be able to see the network traffic.

![image](https://user-images.githubusercontent.com/18504798/205090609-2d0906af-e636-4718-a915-ed91c9054b78.png)


## View script logs
To view the logcat run:
```
adb logcat -s "MESSENGER_SSL_PINNING_BYPASS:V"
```

[#leftenter](#leftenter)
