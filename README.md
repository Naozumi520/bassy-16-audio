# Better-16-Audio 🎵

## What's This
As the repo named, this is **better-16-audio**, a heavy tweaked audio config to have even better speaker quality on 16inch MacBook Pro (2019/2020) under macOS.

## How is this "better"?
I understand that the term "better" may be subjective. This configuration primarily focuses on boosting the speaker's bass, creating a powerful and immersive audio experience. Although I think it's pretty cool, but it's worth noting that for some users, this might result in speaker distortion at higher volumes. So, whether or not this improves your user experience depends on your personal preferences.

## How do I managed to improve the speaker config?
Apple's audio configuration files are stored in plist format but are encrypted and use a base64-like encoding, making them unreadable. Only Apple knows what the actual values mean. However, Apple's code quality restrictions on employees ensure that these configurations are clean and consistent. By comparing different models' configurations, we can identify which ones are better and more recent.
For example, take a look at this comparison between `Mac-E1008331FDC96864/DSP/Strips/builtin_speaker_out_general.austrip` and `AID9/DSP/Strips/builtin_speaker_out_general.austrip`:

![](docs/Screenshot%202023-05-22%20at%209.39.26%20PM.png)

You can see that "Untitled" isn't look as good as "vareq_4_22_21", which should be a more recent Apple employee's achievement. By altering the encoded values and effect names, I've managed to edit the configuration to create Better-16-Audio! 🚀

## Preview
https://github.com/Naozumi520/better-16-audio/assets/52615455/c7a796e5-04e1-4f50-b07a-3a8a75f1b5fb

Recorded using iPhone 13 Pro

## Installation

> **Warning**
**Write Access unlock on Root Volume and SIP disable are required**  
Follow this article: [Follow this article: How to Enable Write Access on Root Volume on macOS Big Sur and Later](https://elitemacx86.com/threads/how-to-enable-write-access-on-root-volume-on-macos-big-sur-and-later.652/)

> **If your machine is MacBookPro16,4 not MacBookPro16,1: instead of `Mac-E1008331FDC96864`, use `Mac-A61BADE1FDAD7B05` as target folder as they are not the same**

1. Download and unzip this repository. 📁  
2. Copy builtin_speaker_out_general.austrip to /Users/naozumi/livemount/System/Library/Audio/Tunings/Mac-E1008331FDC96864/DSP/Strips and replace the old file. 🔄  
3. Copy builtin_speaker_out.dspg to /Users/naozumi/livemount/System/Library/Audio/Tunings/Mac-E1008331FDC96864/DSP/Graphs and replace the old file. 🔄  
4. Copy cfg19152-aumx-3dem-appl.aupreset to /Users/naozumi/livemount/System/Library/Audio/Tunings/CFG19152/AU and replace the old file. 🔄  

To save the changes, use the following command: 🖥️

```zsh
sudo bless --folder ~/livemount/System/Library/CoreServices --bootefi --create-snapshot
```

Enjoy your **enhanced audio** experience! 🎉
