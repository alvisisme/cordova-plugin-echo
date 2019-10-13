# Cordova Echo Plugin

Simple Cordova plugin that helps to echo the message and it will support Android platforms.

## Two kind of Echo messages plugins.

    1. Thread-safe callback.    
    2. Non Thread-safe callback.

## Using
Clone the plugin

    $ git clone http://gitlab.developer.com/cordova/cordova-plugin-echo.git

Create a new Cordova Project

    $ cordova create echo com.uviexample.uviechoapp Echo
    
Install the plugin

    $ cd echo
    $ cordova plugin add ../cordova-plugin-echo
    

Edit `www/js/index.js` and add the following code inside `onDeviceReady` and save the file.

```js
var success = function(message) {
    alert(message);
}

var failure = function() {
    alert("Error calling Echo Plugin");
}

echo.threadFunction("Echo me - thread!!!", success, failure);
echo.nonThreadFunction("Echo me - nonthread!!!", success, failure);
```

Install Android platform

```bash
cordova platform add android
```

Build the code 

```bash
cordova build
```    
    
Run the code

```
cordova run
```
