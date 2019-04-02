# Excel Version

**Name:** Excel Version
**Description:** Reports the installed version of Microsoft Excel for Mac
**Return Type:** string
**Language:** nash

## Code
~~~~ 
if [ -d /Applications/Microsoft\ Excel.app ]; then
    AppVersion=`/usr/bin/defaults read /Applications/Microsoft\ Excel.app/Contents/Info.plist CFBundleShortVersionString`
    echo $AppVersion
else
    echo "Not installed"
fi

exit 0
~~~~
