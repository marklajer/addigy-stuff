# MAU Channel

**Name:** MAU Channel
**Description:** Reports the effective Channel of Microsoft AutoUpdate for Mac
**Return Type:** string
**Language:** bash

## Code
~~~~ 
if [ -d /Library/Application\ Support/Microsoft/MAU2.0/Microsoft\ AutoUpdate.app ]; then
    ChannelName=`python -c "from Foundation import CFPreferencesCopyAppValue; print CFPreferencesCopyAppValue('ChannelName', 'com.microsoft.autoupdate2')"`
    if [ "$ChannelName" == "External" ]; then
    	echo "Insider Slow"
    elif [ "$ChannelName" == "Insider_Fast" ]; then
    	echo "Insider Fast"
    elif [ "$ChannelName" == "Internal" ]; then
    	echo "Microsoft"
    elif [ "$ChannelName" == "Dogfood" ]; then
    	echo "Dogfood"
    elif [ "$ChannelName" == "Custom" ]; then
    	ManifestServer=`python -c "from Foundation import CFPreferencesCopyAppValue; print CFPreferencesCopyAppValue('ManifestServer', 'com.microsoft.autoupdate2')"`
    	echo "Custom - $ManifestServer"
    else
    	echo "Production"
    fi
else
    echo "Not installed"
fi

exit 0
~~~~
