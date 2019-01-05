# udev video examples

Examples of udev rules for video capture devices. I have used these for my SageTV setup, but they are not specific
to SageTV and could be used as examples for other systems.

Most of these rules were to make sure that the same video capture card appeared as the same video device under Linux after every boot.
This was important because I was using something other than the card itself (a IR blaster to a STB) to tune channels.
I needed to make sure the defined "Video Source" in SageTV (which corresponded to the Linux device) was matched to the correct
IR blaster.

In some cases it was challenging to find a unique udev parameter to identify each device. For the multiple PVR-500s
I had to map them based on PCI slots (using the KERNELS parameter) which required some experimentation.

For most of these examples you'll need to tweak them for your own setup. You'll likely have to determine and update the examples with one or following for your own setup:
* What parameters to use to identify your computer's PCI Slots
* Serial numbers for your device

The rules files (with your customizations) should be placed in `/etc/udev/rules.d`.

Multiple files can be used together but you **will** need to adjust the device name numbering,
as the examples all default to starting with the 0th device. That is, `video0` can only be used once,
so if you use multiple files that assign `video0` you'll need to renumber all except one of them.
Be especially careful if you renumber the PVR-500 device names, as the PCM and YUV encoder
number for each device isn't always obvious.
