# Shairport-Sync-Hardware-Volume
Hardware volume control code for Mike Brady's Shairport Sync Code (or any other Raspberry Pi with ALSA installed)

This is a volume control software designed to be used with Mike Brady's Shairport Sync software that uses a rotary encoder attached to the GPIO to control the volume and mute the audio. It also uses Bob Rathbone's very helpful rotary encoder class, which is inluded in the code.

# Installation/Use instructions
At the moment, as the python code does not run as a daemon, it needs to be called specially. The way I have it running on my machine is that the code (as a normal python file, does not necessarily need the '.py' ending, as long as it is 'chmod'ed suitably) is copied into /usr/bin/ which allows it to be cakked
