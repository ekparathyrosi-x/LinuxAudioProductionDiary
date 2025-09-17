# Operating System
As the candidate operating system distribution to replace Windows 10 I chose Ubuntu 24.04 LTS, because I'm more familiar with the Ubuntu distribution, than other Linux distributions.

I had heard about Ubuntu Studio distribution existing, and was initially planning to install it. Ubuntu Studio is an Ubuntu variant that should include software package suites for creative work, including audio. However, I found out that Ubuntu Studio uses KDE desktop environment, and that there's a separate package manager to install the Ubuntu Studio packages to other Ubuntu flavors. It's been awhile since I last used KDE, so I chose the regular Ubuntu with the Ubuntu studio package. I might try the real KDE based Ubuntu Studio later, to see wheter it delivers a different experience.

With Ubuntu and the Ubuntu Studio package I had some unnecessary problems at first. I may have had a wrong idea of what the packages installed by Ubuntu Studio do, but the initial experience was a bit crude. The Ubuntu Studio package manager let's you install audio software such as Ardour daw, MuseScore and plugins. But under the regular Ubuntu it was not easy to find out what software was installed by Ubuntu Studio, what it was and where it was located. But there was a script to rearrange application icons in Ubuntu app launcher. This part may be something that might be clearer for beginners in the actual KDE based Ubuntu Studio. However, in audio production one might not need to access stand alone software from application launcher and in stead use plugins from a DAW.


## Audio system
For linux there are multiple audio systems with different properties. Selecting the correct audio system and configuration is important to get adequate performance ie. low enough latency. This is similar to how on Windows one would need to activate the ASIO drivers in stead of what Windows might default to.

For Linux there's at least PulseAudio, ALSA, Jack and PipeWire.
PulseAudio is good for regular consumer use. It allows multiple applications to play sound, but it has too high latency for audio production.
ALSA is a low level system which achieves low latency, but multiple applications might not be able to play sound.
Jack and PipeWire allow multiple applications to play sounds and routing of audio and midi between applications, inputs and outputs. Low latency can also be achieved with Jack and PipeWire.

I had previously used Jack when testing plugins in Linux. Ubuntu (or Ubuntu Studio) however uses PipeWire as the default audio system. 

## Low-latency kernel
While initially reading about Ubuntu Studio, in addition to the included software I was interested in the low-latency kernel that would be available.

I installed the low-latency kernel, but there was a catch. 3rd party GPU driver didn't work with the low-latency kernel and second display would stay blank without the driver.

I tried using the open source GPU driver with the low-latency kernel, however there was another issue. If the displays went to sleep, there was a chance that the system froze, one display didn't wake up and I couldn't log in again before rebooting.

In the end I ended up reverting to regular non low-latency kernel and 3rd party GPU driver. So far it seems, that the regular kernel is enough.

## Alternatives
On forums I came across while searching for solutions to issues, other people favored distributions such as Arch Linux, Manjaro and Fedora.

## Summary
I installed Ubuntu and the Ubuntu Studio packages, but there are other options too.

Ubuntu Studio provides a bunch of apps and packages for audio production, but the versions might be quite old.

The default settings were pretty good. Messing with the audio system settings was in vain. In the end the default PipeWire seems to work, but there was some issues with configuring Reaper DAW, which I'll describe later.

I installed packages and low latency kernel, but low latency kernel conflicted with GPU drivers. So far regular kernel seems to work well enough.

In the end the Ubuntu Studio Installer was able to install the packages, but the installer tool itself wasn't great to use and crashed multiple times leaving me wondering what did or didn't install.
