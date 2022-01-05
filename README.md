# appium-with-python-tutorial

Appium
- https://appium.io/

Android Verison History
- https://en.wikipedia.org/wiki/Android_version_history


<img width="1246" alt="Screen Shot 2022-01-02 at 16 20 26" src="https://user-images.githubusercontent.com/51218415/147890868-79123380-3883-420f-8a75-3a0490898b0f.png">

Pre-requisite for Windows and MAC OSX:
- Python
- PyCharm / VSCode - https://code.visualstudio.com/download
- Java JDK 1.8 (and set JAVA_HOME env variable)
- NodeJS - https://nodejs.org/en/
- Android Studio (and set ANDROID_HOME env variable) - https://developer.android.com/studio 
- Appium GUI / Desktop App - https://appium.io/
- Appium-Python-Client

```
brew install android-platform-tools
```

### Useful mirroring tool for Android devices

```
brew install scrcpy
```

Connect your cellphone to the PC and run the command

```
scrcpy
```

## Intro

### Updating to Appium 2.0 Python client

```
pip install Appium-Python-Client==2.1.2
```

```python
from appium import webdriver
import time

desired_caps = dict(
    deviceName="Android",
    platformName="Android",
    browserName="Chrome"
)

driver = webdriver.Remote("http://127.0.0.1:4723/wd/hub", desired_caps)

driver.get("http://google.com")
print(driver.title)
time.sleep(2)
driver.quit()
```

## Different ways to starting appium server

## Automating Native Apps

### Automating Dialer App - Making a phone call

```
adb devices
```

```
adb shell
```

```
dumpsys window windows | grep -E 'mTopActivityComponent'
```

```python
from appium import webdriver
import time

desired_caps = dict(
    deviceName="Android",
    platformName="Android",
    appPackage="com.android.dialer",
    appActivity=".BBKTwelveKeyDialer"
    
)

driver = webdriver.Remote("http://127.0.0.1:4723/wd/hub", desired_caps)

time.sleep(2)
driver.quit()
```

```python
from appium import webdriver
import time

desired_caps = dict(
    deviceName="Android",
    platformName="Android",
    appPackage="com.zhiliaoapp.musically",
    appActivity="com.ss.android.ugc.aweme.main.MainActivity"
    
)

driver = webdriver.Remote("http://127.0.0.1:4723/wd/hub", desired_caps)

time.sleep(2)
driver.quit()
```
