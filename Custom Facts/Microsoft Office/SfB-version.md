# SfB Version

**Name:** SfB Version
**Description:** Reports the installed version of Microsoft Skype for Business for Mac
**Return Type:** string
**Language:** bash

## Code
~~~~ 
    if [ -d /Applications/Skype\ for\ Business.app ]; then
    AppVersion=`/usr/bin/defaults read /Applications/Skype\ for\ Business.app/Contents/Info.plist CFBundleShortVersionString`
    echo $AppVersion
	else
	    echo "Not installed"
	fi

	exit 0
~~~~
