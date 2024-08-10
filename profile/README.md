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
    
  + Since I did not like this approach, my goal was to develop a mainboard that integrates all the hardware for eye and face tracking. This includes three ESP32-S2R8s, a USB hub, and a way to safely power the IR LEDs used to illuminate the eyes and face.
  + During the project, I also noticed that I wanted to add a connection for a fan and a USB port that could be used, for example, for low-power Bluetooth LE sticks. Additionally, I have developed PCBs and 3D models to make the attachment of the IR LEDs and camera to the lens easier.

### Goal:
My goal with the project is to contribute to the broader adoption of face tracking and, especially, eye tracking. In my opinion, both technologies have immense potential, ranging from enhancing social VR experiences to techniques like foveated rendering, ultimately advancing VR as a whole. 
<br/><br/>

## Why only for Index?:
  + The Index is the headset I have and use. It is also very popular and, due to its size, offers the possibility to accommodate the necessary hardware relatively efficiently.

  + I won’t rule out the possibility of developing solutions for other headsets in the future, such as the Bigscreen Beyond or a wireless version for the Quest. However, due to its small size, the Beyond presents an even greater challenge. Additionally, I don’t have any     other headsets and would need to acquire them first, which would be a significant investment.

  + Therefore, the hardware is currently available only for the Index. But you never know what the future might bring.



## Thank you:

### Software:
  + Eye Tracking: [EyeTrackVR](https://github.com/EyeTrackVR/EyeTrackVR)
  + Face Tracking: [Project Babble](https://github.com/Project-Babble)
