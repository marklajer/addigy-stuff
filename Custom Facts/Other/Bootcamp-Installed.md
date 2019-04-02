# Bootcamp Installed

**Name:** Bootcamp Installed
**Description:** Return if bootcamp is installed or not.
**Return Type:** boolean
**Language:** bash

## Code
~~~~ 
BOOTCAMP_DETECT=$( /usr/sbin/diskutil list | grep -c "Microsoft Basic Data" )

if [[ "${BOOTCAMP_DETECT}" == "1" ]]; then
      result=Yes
      echo "True"
   else
      result=No
      echo "False"
fi
~~~~
