# Outlook Version

**Name:** Outlook Version
**Description:** Reports the installed version of Microsoft Outlook for Mac
**Return Type:** string
**Language:** bash

## Code
~~~~ 
    if [ -d /Applications/Microsoft\ Outlook.app ]; then
    AppVersion=`/usr/bin/defaults read /Applications/Microsoft\ Outlook.app/Contents/Info.plist CFBundleShortVersionString`
    echo $AppVersion
	else
	    echo "Not installed"
	fi

	exit 0
~~~~
