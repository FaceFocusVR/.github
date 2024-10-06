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
  > E_{IR} = \sum_{780}^{3000} E_{\lambda} \cdot \Delta \lambda \leq 100 \ \quad\quad [\frac{\text{W}}{\text{m}^2}] \quad \quad \text{for } (t > 1000 \ \text{s})
  > $$
  > 
  > Where:
  > - **Eλ** is the spectral irradiance in W·m⁻²·nm⁻¹,
  > - **Δλ** is the bandwidth in nm,
  > - **t** is the exposure duration in seconds.
<br/><br/>

This formula itself isn't of primary interest to us. What is far more relevant is the limit it sets:

$$
E_{IR} \leq 100 \ \frac{\text{W}}{\text{m}^2} = 10 \ \frac{\text{mW}}{\text{cm}^2}  \quad\quad \text{ for } (t > 1000 \ \text{s})
$$

<br/><br/>







## Calculations
### Datasheet

The following can be extracted from the LED datasheet:

**Radiation Intensity:** Min 3, Max 8 mW/sr  
I choose 8 mW/sr as it represents the worst-case scenario, indicating the maximum output of the LED. This means that the LED emits 8 milliwatts of optical power per steradian<sup>2</sup> when operated at a forward current of 20 mA. Since the LED is limited to 2.4 mA due to the board design, and the datasheet indicates that the radiation intensity decreases linearly, we can calculate the adjusted radiation intensity as follows:

  $$
  \text{Adjusted Radiation Intensity} = \left( \frac{8 \ \text{mW/sr} \times 2.4 \ \text{mA}}{20 \ \text{mA}} \right) = 0.96 \ \text{mW/sr}
  $$

  <br/><br/>
**Half Light Angle:** 120 Degrees  
This indicates that the LED radiates light within a cone of 120 degrees. The half light angle is the angle at which the emitted intensity falls to half of its maximum value. A wider angle provides broader illumination, making the LED suitable for applications requiring diffuse lighting.
<br/><br/>

<sup>2</sup> A steradian is a unit used to measure angles in three-dimensional space, similar to how a radian measures angles in a circle.
<br/><br/>
<br/><br/>
<br/><br/>






### Solid Angle and Illuminated Area
Currently, we only have a value indicating the LED's power output within a 120-degree cone. To calculate the power per unit area specifically at the eye, we need two additional parameters: the size of the illuminated area and the distance from the light source.

To determine the illuminated area, we need the "surface area" of the place where the light cone formed by the LED intersects with the eye, which varies based on the distance from the light source. This area can be calculated using the solid angle, which measures the three-dimensional space occupied by the light as it emanates from a point source, defined in steradians.
<br/><br/>
<br/><br/>

To calculate the solid angle $$\(Ω\)$$ for a specific emission angle, we use the half angle $$\(θ\)$$.

The given emission angle is $$\(120^\circ\)$$. Since we need the half angle for the calculation, we divide the emission angle by 2:

$$
θ = \frac{120^\circ}{2} = 60^\circ
$$

The formula for calculating the solid angle $$\(Ω\)$$ in steradians is:

$$
Ω = 2\pi \left(1 - \cos(θ)\right)
$$

Now we substitute the value for $$\(θ = 60^\circ\)$$ into the formula. First, we need to calculate the cosine of $$\(60^\circ\)$$, which is $$\(0.5\)$$:

$$
\cos(60^\circ) = 0.5
$$

Now we insert this value into the formula:

$$
Ω = 2\pi \left(1 - \cos(60^\circ)\right) = 2\pi \left(1 - 0.5\right)
$$

Next, we simplify the calculation:

$$
Ω = 2\pi \times 0.5 = \pi \ \text{sr}
$$

<br/><br/>
<br/><br/>
The area $$\(A\)$$ onto which the light from an LED is distributed at a certain distance $$\(r\)$$ can be calculated using the following formula:

$$
A = r^2 \cdot Ω
$$

<br/><br/>
We have already calculated the solid angle \(Ω\) for the emission angle of $$\(120^\circ\)$$, which is $$\(π \ \text{sr}\)$$.

A distance between the eye and the LED of r = 1 cm is assumed, but even 0.5 cm meets the standards.

Now we calculate the area:

$$
A = 1 \, \text{cm}^2 \cdot π
$$

$$
A \approx 1 \cdot 3.14 \ \text{cm}^2 \approx 3.14 \ \text{cm}^2
$$

<br/><br/>
These 3.14 cm² describe the area that the IR radiation covers at a distance of 1 cm from the LED, independent of the size of the eye. Since the LEDs are positioned on the outside of the eye, a significant portion of the radiation is already lost to the sides. Additionally, the surface area of the eye is much smaller than 3.14 cm². Consequently, the eye receives only a fraction of the radiation distributed over the 3.14 cm² area. However, since we are calculating based on the worst-case scenario, we will use the entire area for our calculations.

If you've been paying attention, you might wonder: Why don't I use the smaller area that hits the eye, which would result in a much higher calculated power per cm² and could potentially exceed safe limits?

While this is a valid point, it only holds true when considering distance. At shorter distances, the light cone narrows, concentrating the radiation on a smaller area and thereby increasing the density, essentially scaling it.

However, in my calculations, I do not scale the radiation. Instead, I consider the total area of 3.14 cm², from which only a small fraction actually reaches the eye. For example, only about 0.14 cm² may illuminate the eye, while the remaining area dissipates into the environment. If I were to calculate using just 0.14 cm², it would inaccurately suggest that all the radiation concentrates on that small area, overlooking the significant portion that is lost.
<br/><br/>
<br/><br/>













### Irradiance (Power Density)

Now we can convert the adjusted radiation intensity from mW/sr to mW/cm²:

The power density in mW/cm² can be calculated using the formula:

$$
\text{Power Density} \ \text{[mW/cm}^2] = \frac{\text{Adjusted Radiation Intensity} \ \text{[mW/sr]}}{A \ \text{[cm}^2]}
$$

Now, substituting the given values into the formula:

$$
\text{Power Density} \ (\text{mW/cm}^2) = \frac{0.96 \ \text{mW/sr}}{3.14 \ \text{cm}^2}
$$

Now, calculate the value:

$$
\text{Power Density} \approx \frac{0.96}{3.14} \approx 0.305 \ \text{mW/cm}^2
$$

Since four LEDs are used on each eye, this result must be multiplied by four.

$$
\text{Total Power Density} = 0.305 \ \text{mW/cm}^2 \times 4 \approx 1.22 \ \text{mW/cm}^2
$$

<br/><br/>

## Result
If the LEDs are 1 cm away from your eye, the radiation they emit is 1.22 mW/cm², which is well below the maximum limit of 10 mW/cm². Even if the distance were halved (which is not physically possible) and the LEDs were 0.5 cm away, the radiation would increase to 4.88 mW/cm², still half of the limit.

