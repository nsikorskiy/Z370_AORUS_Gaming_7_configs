# Pulseaudio configs 

This configs fix problem which switch from headfones and rear line out.


Files:

* "lib/udev/rules.d/91-pulseaudio-Z370AG7.rules"

  udev rules, for set profile

* "usr/share/pulseaudio/alsa-mixer/profile-sets/Z370AG7.conf"

  profile

* "usr/share/pulseaudio/alsa-mixer/paths/analog-output-iec958-Z370AG7.conf"

  Configure  optical spdif. 

  mutt switch "IEC958 16".  If it is turned off, then the toslink has no light.
  I do not have an adapter for the built-in board output. It is not known how 
  to manage it. Maybe it's connected together with the optical one, but maybe not.

* "usr/share/pulseaudio/alsa-mixer/paths/dp-output-Z370AG7.conf"
  Configure DP out, and set enable switch.

  it hdmi3 event.

  mutt switch "IEC958 2"

* "usr/share/pulseaudio/alsa-mixer/paths/hdmi-output-Z370AG7.conf"

  Configure HDMI out, and set enable switch

  it hdmi1 event

  mutt switch "IEC958 1"

* "usr/share/pulseaudio/alsa-mixer/paths/analog-output-lineout-Z370AG7.conf"
* "usr/share/pulseaudio/alsa-mixer/paths/analog-output-headphones-Z370AG7.conf"

  path for lineout and headphones.

  Volume "Front" not connected. To adjust the volume, use "headphones". Switch "Front"
  disable rear line out. Switch "headphones" disable front headfones out. Most likely, 
  both these outputs are connected to an external DAC, and the headphone volume controls 
  this DAC. Now volume control "headphones" merged instead of "off". 

  Volume "Front"ignored.


~~* "usr/share/pulseaudio/alsa-mixer/paths/iec958-stereo-output-Z370AG7.conf"~~

  ~~SPDIF is lit if there is sound through analog stereo if IEC958 16 is enabled. I can not test~~
  ~~because they do not have SPDIF devices. Perhaps through it there is an audio stream and maybe~~
  ~~there is silence until "IEC958 Default PCM".~~

  ~~If this is the case, then you can use SPDIF as the third way for analog stereo.~~
  
  "IEC958 16" is  "IEC958",index=16. puseaudio not support element index.  LOL, in 2018 puseaudio not support element index.


## Install:
* sudo cp -a lib usr /
* reboot




