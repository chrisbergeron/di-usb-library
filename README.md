Disney Infinity USB Base Library
================================

Python3 skeleton code for interfacing with a USB Disney Infinity Skylanders NFC reader.  This is a Python3 fork of the original dl-usb-library:
https://github.com/techbelly/di-usb-library

Read more about this project at:  https://chrisbergeron.com/2022/01/08/time-tracking-with-a-disney-infinity-usb-nfc-reader/

This code has been Tested with the PS3/4 and Wii U hardware versions.  The XBox360 base is likely different.

Sample code:

```python

from infinity import InfinityBase

base = InfinityBase()

# this will be run whenever a figure or disk is added/removed
base.onTagsChanged = lambda: print("Tags added or removed.")

base.connect()

# get all the figures and disks on the base 
base.getAllTags(print)

base.setColor(1, 200, 0, 0)

base.setColor(2, 0, 56, 0)

base.fadeColor(3, 0, 0, 200)

time.sleep(3)

base.flashColor(3, 0, 0, 200)

while True:
    pass
    
```

Example output:

```bash
Connected to Disney Infinity USB Device 297

Activate Message =  [40, 99, 41, 32, 68, 105, 115, 110, 101, 121, 32, 50, 48, 49, 51]
Leave construct_message with message = [0, 255, 17, 128, 1, 40, 99, 41, 32, 68, 105, 115, 110, 101, 121, 32, 50, 48, 49, 51, 183, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]

Message is:  [0, 255, 17, 128, 1, 40, 99, 41, 32, 68, 105, 115, 110, 101, 121, 32, 50, 48, 49, 51, 183, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
Leave construct_message with message = [0, 255, 2, 161, 2, 164, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]

Message is:  [0, 255, 2, 161, 2, 164, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
Leave construct_message with message = [0, 255, 6, 144, 3, 1, 200, 0, 0, 97, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]

# Placed tag on Red square
Tags added or removed.
[171, 4, 1, 0, 0, 0, 176, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]

# Removed tag from Red square
Tags added or removed.
[171, 4, 1, 0, 0, 1, 177, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]

# Placed tag on 
Tags added or removed.
[171, 4, 2, 0, 0, 0, 177, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
```


