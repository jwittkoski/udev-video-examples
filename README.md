# udev-video-examples

Examples of udev rules for video capture devices. I have used these for my SageTV setup, but they can be used for any purpose.

Most of these rules were to make sure that the same video capture card appeared as the same video device under Linux every time.
This was important because I was using something other than the card itself (a IR blaster to a STB) to tune channels.
I needed to make sure the Video Source in SageTV (which corresponded to the Linux device) was matched to the correct
IR blaster.
