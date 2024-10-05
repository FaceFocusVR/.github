# Safety

No system is 100% secure, but I’ve done everything possible to protect both the hardware where the mainboard is installed, the mainboard itself, and of course, your eyes.

Do not attempt to replace, repair, or disable any safety-related circuits or components yourself! Although we are exposed to infrared radiation daily, it can be harmful in excessive doses!

Even though I check each IR LED on kits that i sell, the risk of use lies with the user. The safety measures are designed to REDUCE potential failure risks, but all further safety responsibilities fall on the user. This includes ensuring you do not feel warmth, excessive eye strain, or experience short-term effects like dark spots or dry/warm eyes during use.

**I have tried to make FaceFokusVR as safe as possible, but I do not take responsibility for any damage incurred.**
<br/><br/>

## Basics
  + The safety measures and calculations are primarily based on the guidelines provided by the EYETrackVr team. However, I have independently verified and expanded upon these measures, offering a more detailed explanation of the protective measures implemented to meet the requirements. You can find the safety guidelines from the EYETrackVr team here: [IR Emitter Safety / EyeTrackVR](https://docs.eyetrackvr.dev/getting_started/led_safety)

  + Infrared (IR) radiation is used in eye-tracking systems to illuminate the eye without being visible to the human eye. IR radiation is measured in terms of irradiance, which quantifies the power of radiation over a specific area (measured in mW/cm²). For safety, it’s important to keep irradiance levels below recommended limits, as excessive exposure can lead to thermal damage to the cornea and long-term risks like cataracts. IR light can also cause discomfort or strain if too intense, which is why it is essential to calculate safe exposure levels, considering both the power of the LEDs and their distance from the eye.


### EN 62471
  
To avoid thermal injury of the cornea and possible delayed effects upon the lens of the eye (cataractogenesis), ocular exposure to infrared radiation (EIR) over the wavelength range of **780 nm to 3000 nm** should be considered. [EN 62471 Page 41]

For times greater than **1000 s**, the limit becomes:

$$
E_{IR} = \sum_{780}^{3000} E_{\lambda} \cdot \Delta \lambda \leq 100 \, [\text{W} / \text{m}^{2}] \quad \text{for} (t > 1000 \, \text{s})
$$

Where:
- **Eλ** is the spectral irradiance in W·m⁻²·nm⁻¹,
- **Δλ** is the bandwidth in nm,
- **t** is the exposure duration in seconds.






