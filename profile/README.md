# FaceFocusVR

FaceFocusVR is a project I developed to offer a clean and plug-and-play solution for retrofitting eye and face tracking to existing VR headsets.

This project focuses exclusively on the hardware. The software I use for eye and face tracking is open-source and linked below.

Currently, the hardware is only available for the Valve Index, but additional headsets may be supported in the future depending on demand.
<br/><br/>

## Quicklinks:
  + Everything you need: [Project Website](TBD)
  + Get FaceFocusVR Hardware: [How To Buy/DIY](https://github.com/FaceFocusVR/.github/blob/main/README_BUY.md)
  + Need Support?: [Discord](TBD)
<br/><br/>

## Why FaceFocusVR?:
  + The current approach for adding face tracking and eye tracking to most headsets involves attaching multiple ESP32s, such as the Seeed Xiao ESP32-S3 Sense, and a USB hub to the headset. Alternatively, you can disassemble an existing USB hub and attempt to solder the        ESP32s directly onto the hub to save space.
    
  + Since I did not like this approach, my goal was to develop a mainboard that integrates all the hardware for eye and face tracking. This includes three ESP32-S2R8s, a USB hub, and a controller for the IR LEDs used to illuminate the eyes and face.

Basic technic

## Thank you:

### Software:
  + Eye Tracking: [EyeTrackVR](https://github.com/EyeTrackVR/EyeTrackVR)
  + Face Tracking: [Project Babble](https://github.com/Project-Babble)
