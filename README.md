## Shadowsocks for Android

A [shadowsocks](http://shadowsocks.org) client for Android, written in Scala.

Help to translate shadowsocks: http://crowdin.net/project/shadowsocks/invite

[![Google Play](http://developer.android.com/images/brand/en_generic_rgb_wo_45.png)](https://play.google.com/store/apps/details?id=com.github.shadowsocks)

### TRAVIS CI STATUS

[![Build Status](https://secure.travis-ci.org/shadowsocks/shadowsocks-android.png)](http://travis-ci.org/shadowsocks/shadowsocks-android)

### PREREQUISITES

* JDK 1.6+
* SBT 0.12.3
* Android SDK r21+
* Android NDK r9+

### BUILD

* Set environment variable `ANDROID_HOME` to `/path/to/android-sdk`
* Set environment variable `ANDROID_NDK_HOME` to `/path/to/android-ndk`
* Create your key following the instructions at http://developer.android.com/guide/publishing/app-signing.html#cert
* Put your key in ~/.keystore
* Create `local.properties` from `local.properties.example` with your own key information
* Invoke the building like this

```bash
    git submodule update --init

    # Build native binaries
    ./build.sh
    
    # Build the App
    sbt clean android:package-release
```

#### BUILD on Mac OS X (with HomeBrew)

* Install Android SDK and NDK by run `brew install android-ndk android-sdk`
* Add `export ANDROID_HOME=/usr/local/Cellar/android-sdk/$version` to your .bashrc , then reopen the shell to load it.
* Add `export ANDROID_NDK_HOME=/usr/local/Cellar/android-ndk/$version` to your .bashrc , then reopen the shell to load it.
* echo "y" | android update sdk --filter tools,platform-tools,build-tools-21.0.1,android-21,extra-google-m2repository --no-ui --no-https -a
* echo "y" | android update sdk --filter extra-android-m2repository --no-ui --no-https -a
* Create your key following the instructions at http://developer.android.com/guide/publishing/app-signing.html#cert
* Put your key in ~/.keystore
* Create `local.properties` from `local.properties.example` with your own key information .
* Invoke the building like this

```bash
    git submodule update --init

    # Build native binaries
    ./build.sh

    # Build the apk
    sbt clean android:package-release
```

### LICENSE

Copyright (C) 2014 Max Lv <max.c.lv@gmail.com>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.
