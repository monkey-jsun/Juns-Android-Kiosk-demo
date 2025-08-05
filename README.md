# Objective

Android device boots into a single app and stays there forever.  We will use Lock Task feature in Android.

Need Android 13+.

# The solution

1. Use full immersive GUI settings to hide all system UI components (such as notification bar)
2. call startLockTask() to enter kiosk mode

A few problems
1. avoid user prompt on starting lock task:  a) factor reset device; b) install app & set app as device owner (via adb or other means); c) kiosk app white-list itself for task locking
2. boot straight to the app: add receiver to monitor BOOT_COMPLETE broadcast

# Alternatives
1. make kiosk app as launcher (this makes it hard to switch back or escape to regular launcher).  Or write a jumper code as a launcher that starts either kiosk app or original launcher, depending the conditions
