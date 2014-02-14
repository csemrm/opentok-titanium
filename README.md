opentok-titanium-mobile
================
A module for the Titanium Mobile platform that uses the Opentok iOS SDK for video streaming capabilities.

Installation
------------
1.  Download the latest release from the [Releases](https://github.com/opentok/opentok-titanium-mobile/releases) page.

2.  Move the zip file (`com.tokbox.ti.opentok-iphone-x.x.x.zip`) to your application directory, and unzip it
    (e.g. `unzip com.tokbox.ti.opentok-iphone-x.x.x.zip`). The module should now be placed inside the
    `AppRoot/modules/iphone/com.tokbox.ti.opentok/x.x.x/` directory.

Building
------------
If you want to build the code on your own, follow these instructions. If you just want to use the module, scroll down to Usage.

1.  Clone or download the repo.

2.  Run `./download-opentok-native-sdk.sh` to download OpenTok.framework into the appropriate place.

3.  Run `./build.py` to build the module.

4.  Copy the zip (`com.tokbox.ti.opentok-iphone-x.x.zip`) to your application directory:
    `cp com.tokbox.ti.opentok-iphone-x.x.zip /path/to/app/`.

Usage
-----
1.  Declare the module in your `tiapp.xml` file:
    NOTE: the version attribute of the module tag should match the release you downloaded.

    ```xml
    <modules>
      <module version="x.x.x">com.tokbox.ti.opentok</module>
    </modules>
    ```

2.  Load the module in your application

    ```javascript
    var opentok = require('com.tokbox.ti.opentok');
    ```
	
3.  Create and connect to a session

    ```javascript
    var CONFIG = {
      apiKey: '...',    // Get from your Project page on the Developer Dashboard (https://dashboard.tokbox.com/projects)
      sessionId: '...', // Generated by server-side SDK
      token: '...'      // Generated by server-side SDK
    };
    var session = opentok.createSession({ sessionId: CONFIG.sessionId });
    session.connect(CONFIG.apiKey, CONFIG.token);
    ```

4.  For more details, see the [module documentation](documentation/index.md) and the 
    [example](https://github.com/opentok/Opentok-Titanium-HelloWorld).

Requirements
------------
*  Titanium SDK 3.1.0.GA or later
*  iOS SDK 6.1 or later
*  Opentok API Key. [Get one here](https://dashboard.tokbox.com/signups/new).
*  OpenTok.framework requires projects to be built for only armv7 (device); i386 (simulator), armv6, armv7s, and arm64 are not supported.

Getting Help
------------

You can find help by posting your question to the [Github Issues](https://github.com/opentok/opentok-titanium-mobile/issues)
page, posting on the [TokBox forums](http://www.tokbox.com/forums/), or asking in the 
[#opentok IRC channel](http://www.tokbox.com/support/officehours).

Known Issues
------------

If you are experiencing any problems, please look at the [Github Issues](https://github.com/opentok/opentok-titanium-mobile/issues)
page for known issues.

Notes
-----
*  OpenTok.framework can be downloaded from the [official repo](https://github.com/opentok/opentok-ios-sdk-webrtc)
*  Using the Simulator is currently not supported.
*  The API is currently a mix of the Opentok web API, iOS specifics, and Titanium conventions. These are subject
   to change. Suggestions welcome.
*  Open source contributions welcome :)

License
-------
Copyright (c) 2012 TokBox, Inc.
Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in 
the Software without restriction, including without limitation the rights to 
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies 
of the Software, and to permit persons to whom the Software is furnished to do 
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all 
copies or substantial portions of the Software.

The software complies with Terms of Service for the OpenTok platform described 
in http://www.tokbox.com/termsofservice

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR 
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, 
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE 
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER 
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, 
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE 
SOFTWARE.

