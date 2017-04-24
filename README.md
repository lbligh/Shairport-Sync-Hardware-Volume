# Shairport-Sync-Hardware-Volume
Hardware volume control code for Mike Brady's Shairport Sync Code (or any other Raspberry Pi with ALSA installed)

This is a volume control software designed to be used with Mike Brady's Shairport Sync software that uses a rotary encoder attached to the GPIO to control the volume and mute the audio. It also uses Bob Rathbone's very helpful rotary encoder class, which is inluded in the code.

## Installation/Use instructions
The prerequisites for the code to work are python 3.x as well as ALSA installed. I do not know which packages are needed to install ALSA, as I have never needed to do so myself.
The way I have it running on my machine is that the code (as a normal python file, does not necessarily need the '.py' ending, as long as it is 'chmod'ed suitably (`chmod 777 *code*` is the easiest - see `man chmod` for more details)) is copied into `/usr/bin/` which allows it to be called straight from the command line
```
~ $ airplay_volume
```
Then it needs to be called to start at boot-up. At the moment, the python code does not run as a daemon, which means it needs to be called specially, as nothing else will run if you try to run it. Therefore, in `/etc/rc.local` you need to add the line:
```
nohup /usr/bin/airplay_volume >/dev/null 2>&1 &
```
before the `exit 0`. When the code has been edited to run as a daemon natively the repo will be updated and this readme updated also.

For more information about Shairport-Sync please see [his github](http://github.com/mikebrady/shairport-sync).
For more information about the Rotary Encoder class, and almost all of the rotary encoder side of the code please see [Bob Rathbone's Website](http://www.bobrathbone.com/raspberrypi_rotary.htm).
For the original posting on the questions part of Mike Brady's Repo see [here](https://github.com/mikebrady/shairport-sync/issues/504#issuecomment-294286813).

