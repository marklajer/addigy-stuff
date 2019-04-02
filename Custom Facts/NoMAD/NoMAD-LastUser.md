# NoMAD LastUser

**Name:** NoMAD LastUser
**Description:** See NoMAD last user
**Return Type:** string
**Language:** bash

## Code
~~~~ 
# Get current console user
ConsoleUser=`stat -f "%Su" /dev/console`

# Check if current console user has com.trusourcelabs.NoMAD.plist
if [[ -f "/Users/$ConsoleUser/Library/Preferences/com.trusourcelabs.NoMAD.plist" ]]; then
    # Read SignedIn value
    NoMADSignedInValue=$(defaults read "/Users/$ConsoleUser/Library/Preferences/com.trusourcelabs.NoMAD.plist" SignedIn)
    # Check if SignedIn has a value of 1
    if [[ $NoMADSignedInValue == 1 ]]; then
        # Read LastUser value
        NoMADLastUserValue=$(defaults read "/Users/$ConsoleUser/Library/Preferences/com.trusourcelabs.NoMAD.plist" LastUser)
        # Check if LastUser has a value
        if [[ ! -z "$NoMADLastUserValue" ]]; then
            # Add LastUser value to array
            NoMADLastUser=( "${NoMADLastUser[@]}" "$NoMADLastUserValue" )
        fi
    fi
fi

# Return / submit NoMAD LastUser to Custom Fact
echo ${NoMADLastUser[@]}
~~~~
