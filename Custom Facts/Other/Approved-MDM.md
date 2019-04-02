# MDM Approved

**Name:** MDM Approved
**Description:** Return if MDM is approved or not.
**Return Type:** boolean
**Language:** bash

## Code
~~~~ 
macOS_version=$(/usr/bin/sw_vers -productVersion | awk -F'.' '{print $2}')
sub_version=$(/usr/bin/sw_vers -productVersion | awk -F'.' '{print $3}')

if (( macOS_version < 13  || (macOS_version == 13 && sub_version < 4) )); then
    echo "false"
elif profiles status -type enrollment | grep "User Approved" 1>/dev/null 2>&1; then
    echo "true"
else
    echo "false"
fi
exit 0
~~~~
