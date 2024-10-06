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

## News:
  + Welcome :)
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
    
  + Therefore, the hardware is currently only available for the Index. But you never know what the future might bring.
<br/><br/>

## Is it safe?:
**I have tried Everything I can to make FaceFokusVR as safe as possible, but I do not take responsibility for any damage incurred by the use of it.**
<br/><br/>

  + No system is 100% secure! However, I have implemented multiple safety mechanisms to ensure the IR LEDs emit only limited radiation, well below the limits established by recognized studies on safe exposure levels.

  + Do not attempt to replace, repair, or disable any safety-related circuits or components yourself! Although we are exposed to infrared radiation daily, it can be harmful in excessive doses!

+ While I thoroughly check each IR LED I sell, the responsibility for safe usage ultimately lies with the user. Please pay attention to the following:
  + If you feel any warmth on your eys during use, take a break and assess the situation.<sup>1</sup>
  + If you experience excessive eye strain or short-term effects like dark spots or dry/warm eyes, stop immediately.
<br/><br/>

The limits established by recognized institutions for maximum IR radiation are $$10 \ \frac{\text{mW}}{\text{cm}^2}$$. The calculated output from the LEDs I use is $$1.22 \ \frac{\text{mW}}{\text{cm}^2}$$, which is significantly below this limit. This value is also comparable to the normal IR background radiation that eyes receive from the sun, approximately $$1 \ \frac{\text{mW}}{\text{cm}^2}$$.

Detailed explanation of the technical safety features, studies, and calculations regarding safe exposure IR limits: [Safety](https://github.com/FaceFocusVR/.github/blob/main/README_safety.md)
<br/><br/>

## Thank you:

### Software:
  + Eye Tracking: [EyeTrackVR](https://github.com/EyeTrackVR/EyeTrackVR)
  + Face Tracking: [Project Babble](https://github.com/Project-Babble)
