# Cordova Echo Plugin

一个简单的Cordova插件，实现web和native消息互通功能，支持Android平台。

支持两种消息类型

1. 线程安全的回调消息
2. 线程不安全的回调消息

## 如何使用

1. 创建一个cordova工程

    ```bash
    cordova create echo com.uviexample.uviechoapp Echo
    cd echo
    ```

2. 安装插件

    通过git仓库方式安装

    ```bash
    dordova plugin add git+https://github.com/alvisisme/cordova-plugin-echo.git
    ```

    通过本地文件方式安装

    ```bash
    git clone https://github.com/alvisisme/cordova-plugin-echo.git
    cordova plugin add ./cordova-plugin-echo
    ```

3. 接口测试

    编辑 `www/js/index.js` 文件，在 `onDeviceReady` 函数内加入如下语句并保存文件。

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

4. 安装支持平台

    ```bash
    cordova platform add android
    ```

5. 构建应用

    ```bash
    cordova build
    ```    

6. 运行应用

    ```bash
    cordova run
    ```
