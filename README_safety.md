# Safety

**I have tried to make FaceFokusVR as safe as possible, but I do not take responsibility for any damage incurred by the use of it.**

_Even if you're not completely sure but think there might be an issue with the calculations, circuitry, or anything else, please don’t hesitate to contact me!_
<br/><br/>

  + No system is 100% secure! However, I have implemented multiple safety mechanisms to ensure the IR LEDs emit only limited radiation, well below the limits established by recognized studies on safe exposure levels.

  + Do not attempt to replace, repair, or disable any safety-related circuits or components yourself! Although we are exposed to infrared radiation daily, it can be harmful in excessive doses!

+ While I thoroughly check each IR LED in the kits I sell, the responsibility for safe usage ultimately lies with the user. Please pay attention to the following:
  + If you feel any warmth on your eys during use, take a break and assess the situation.<sup>1</sup>
  + If you experience excessive eye strain or short-term effects like dark spots or dry/warm eyes, stop immediately.

<br/><br/>
<sup>1</sup> I have heard from several users of VR headsets with native eye tracking that their eyes feel warmer after extended use. Therefore, a slight warming could be normal; however, I cannot provide any further details on the matter, as I have not found any conclusive data on this. I can only share all the information I have.
<br/><br/>
<br/><br/>









## Basics
  + The safety measures and calculations are primarily based on the guidelines provided by the EYETrackVr team. However, I have independently verified and expanded upon these measures, offering a more detailed explanation of the protective measures implemented to meet the requirements. You can find the safety guidelines from the EYETrackVr team here: [IR Emitter Safety / EyeTrackVR](https://docs.eyetrackvr.dev/getting_started/led_safety)

  + Infrared (IR) radiation is used in eye-tracking systems to illuminate the eye without being visible to the human eye. IR radiation is measured in terms of irradiance, which quantifies the power of radiation over a specific area (measured in mW/cm²). For safety, it’s important to keep irradiance levels below recommended limits, as excessive exposure can lead to thermal damage to the cornea and long-term risks like cataracts. IR light can also cause discomfort or strain if too intense, which is why it is essential to calculate safe exposure levels, considering both the power of the LEDs and their distance from the eye.

  + To establish a foundation and determine what constitutes a harmful exposure limit, I have referenced various studies, sources, and related materials. All of my sources (except for the standards, which are protected by copyright) are linked with page references in the respective sections.
<br/><br/>






### EN 62471

The **EN 62471** is a European standard that provides guidelines for assessing the photobiological safety of light sources and luminaires. It specifically addresses the potential hazards associated with exposure to various types of optical radiation, including ultraviolet (UV), visible, and infrared (IR) radiation.

Regarding harmful exposure limits for infrared radiation with wavelengths ranging from 780 nm to 3000 nm, the standard states:
<br/><br/>
  > + To avoid thermal injury of the cornea and possible delayed effects upon the lens of the eye (cataractogenesis), ocular exposure to infrared radiation (EIR) over the wavelength range of **780 nm to 3000 nm** should be considered. [EN 62471 Page 41]
  > + For times greater than **1000 s**, the limit becomes:
  > 
  > $$
  > E_{IR} = \sum_{780}^{3000} E_{\lambda} \cdot \Delta \lambda \leq 100 \, \quad\quad [\frac{\text{W}}{\text{m}^2}] \quad \quad \text{for } (t > 1000 \, \text{s})
  > $$
  > 
  > Where:
  > - **Eλ** is the spectral irradiance in W·m⁻²·nm⁻¹,
  > - **Δλ** is the bandwidth in nm,
  > - **t** is the exposure duration in seconds.
<br/><br/>

This formula itself isn't of primary interest to us. What is far more relevant is the limit it sets:

$$
E_{IR} \leq 100 \ \frac{\text{W}}{\text{m}^2} = 10 \ \frac{\text{mW}}{\text{cm}^2}  \quad\quad \text{ for } (t > 1000 \, \text{s})
$$












