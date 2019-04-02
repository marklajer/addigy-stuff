# PPT Version

**Name:** PPT Version
**Description:** Reports the installed version of Microsoft PowerPoint for Mac
**Return Type:** string
**Language:** bash

## Code
~~~~ 
    if [ -d /Applications/Microsoft\ PowerPoint.app ]; then
    AppVersion=`/usr/bin/defaults read /Applications/Microsoft\ PowerPoint.app/Contents/Info.plist CFBundleShortVersionString`
    echo $AppVersion
	else
	    echo "Not installed"
	fi
	exit 0
~~~~
