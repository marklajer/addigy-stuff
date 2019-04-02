# MAU Version

**Name:** MAU Version
**Description:** Reports the installed version of Microsoft AutoUpdate for Mac
**Return Type:** String
**Language:** Bash

## Code
~~~~ 
    if [ -d /Library/Application\ Support/Microsoft/MAU2.0/Microsoft\ AutoUpdate.app ]; then
    AppVersion=`/usr/bin/defaults read /Library/Application\ Support/Microsoft/MAU2.0/Microsoft\ AutoUpdate.app/Contents/Info.plist CFBundleShortVersionString`
        echo $AppVersion
    else
        echo "Not Installed"
    fi
~~~~
