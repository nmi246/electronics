https://www.e-consystems.com/blog/camera/technology/what-is-cmos-sensor-size-in-embedded-cameras-how-to-pick-the-right-sensor-size/#:~:text=The%20size%20of%20the%20CMOS,sensor%20size%20or%20optical%20format.


## CMOS: 
CMOS (Complementary Metal-Oxide Semiconductor) is a digital device for capturing light and converting it into electrical signals. It has a photodiode and a transistor switch for each pixel. When light strikes the pixel, it creates a voltage proportional to intensity. The voltage is sampled directly at the pixel. Having an amplifier for each pixel allows the pixel signals to be amplified individually, as shown in the below figure.

CMOS Sensor Architecture:
![image](https://github.com/nmi246/electronics/assets/42329930/c6243466-dd06-4361-821f-6af34fee7122)




## CCD:


## How camera sensor size is measured:
CMOS sensors are generally specified by their physical sizes. The size of the CMOS sensor determines the light-collecting surface area of the sensor. The dimensions of the sensor are defined by the resolution and the pixel size. As you may know, the size of a sensor is often measured in inches. The image sensor format is sometimes referred to as sensor size or optical format.

The value of optical format is the approximate multiplication of the diagonal length of the sensor and 3/2.

Optical format = (3/2) * Diagonal of Sensor

For example, consider the AR1335-CMOS image sensor from onsemi™ that has a sensor size of 4.54×3.42 mm and a diagonal of 5.68 mm. Therefore, the optical format is 5.68*3/2 = 8.52 mm, which is expressed as 1/3.2″.

Likewise, there are several sensor sizes available in the market as shown in the following figure.

![image](https://github.com/nmi246/electronics/assets/42329930/487620d1-c369-4ec9-b577-80b1e22b3d4b)




## CMOS sensor size comparison
The below table shows the comparison of different sensor sizes and the corresponding crop factors:

|Type	| Diagonal (mm)	| Width (mm)	|Height (mm)	| Area (mm²)	| Crop factor |
|---|--|--|--|--|--|
| 1/2″	| 8 |	6.4	|4.8	|30.7	|5.41|
| 1/2.3″	| 7.66	| 6.17	| 4.55	| 28.5	|5.64|
| 1/2.5″	| 7.18	|5.76 |	4.29 |	24.7|6.02|
| 1/3″	| 6	4.8 |	3.6	| 17.3|	7.21|
| 1/3.2″	| 5.68|	4.54	| 3.42	|15.5	|7.61|
| 1/4″	| 4.5	|3.6|	2.7 |	7.92	|10.81|
| 2/3″	| 11	 |8.8 |	6.6|	58.1	|3.93|
| 35mm full-frame	| 43.1–43.3	| 35.8–36	| 23.9–24	| 856–864| 	1

It is important to note that the crop factor is related to the ratio of the camera sensor’s size to a 35 mm film frame.

Crop Factor = Diagonal_35mm / Diagonal_sensor
