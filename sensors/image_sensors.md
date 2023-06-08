## CMOS: Complimentary Metal Oxide Semiconductor
CMOS (Complementary Metal-Oxide Semiconductor) is a digital device for capturing light and converting it into electrical signals. It has a photodiode and a transistor switch for each pixel. When light strikes the pixel, it creates a voltage proportional to intensity. The voltage is sampled directly at the pixel. Having an amplifier for each pixel allows the pixel signals to be amplified individually, as shown in the below figure.

CMOS Sensor Architecture:
![image](https://github.com/nmi246/electronics/assets/42329930/c6243466-dd06-4361-821f-6af34fee7122)

## CCD: Charge Coupled Device
A CCD sensor is an analog device. Below the CCD layer lies the SSR (Serial Shift Register) which is connected to an amplifier on one end and an ADC (Analog to Digital Converter) on the other. The charge in the CCD layer is transferred to the SSR, and then to the amplifier and the ADC. This charge is read from each pixel site to recreate the image. Have a look at the below diagram to understand how the whole process works:

In a CCD sensor, when photons get converted into electric signals, the charge to be converted into voltage is transferred through a limited number of nodes. This would mean that only a few amplifiers and ADCs are in action, which in turn results in less noise in the output image.

Charge transfer process in CCD sensors:
![image](https://github.com/nmi246/electronics/assets/42329930/88e6cf03-24d8-4b9c-a768-4c005bc336d4)


## Key differences between CMOS and CCD?
Both CCD and CMOS technologies use the photoelectric effect to convert packets of light (or photons) into electric signals. Also, these two sensors are made up of pixel wells that collect these incoming photons. The fundamental difference between the two lies in recreating an image from electric signals.

Let us now look at each of these technologies in detail to learn more about their similarities and differences.  

- Sensitivity: Until recently, CCD had an edge over CMOS when it comes to imaging in low light conditions as well as in the NIR (Near Infra-Red) region (we will talk more about low light and NIR imaging in an upcoming section). However, advancements in the CMOS sensor technology are helping it close in on CCD sensors.
- Noise and image quality: Having a lower number of ADCs and amplifiers helps CCD sensors to deliver images with lesser noise in comparison with CMOS sensors. However, sensor manufacturers are consistently coming up with innovative techniques to enhance image quality of CMOS sensors.
- Power consumption: Compared to CCD sensors, CMOS sensors draw less power which is particularly useful in embedded vision systems that have other power-hungry components in them.
- Supply chain and availability: With more sensor manufacturers moving away from the CCD technology, the availability of these sensors has been drastically reduced in the last few years. Also, if you are looking for a CCD supplier, you are likely to end up with fewer options as opposed to a large universe of vendors for CMOS sensors.  
- Cost: CMOS easily wins the race when it comes to cost.


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
| 1/2.5″	| 7.18	|5.76 |	4.29 |	24.7| 6.02 |
| 1/3″	| 6	| 4.8 |	3.6	| 17.3|	7.21 |
| 1/3.2″	| 5.68 |	4.54	| 3.42	| 15.5	| 7.61|
| 1/4″	| 4.5	| 3.6 |	2.7 |	7.92	| 10.81|
| 2/3″	| 11	 | 8.8 |	6.6|	58.1	| 3.93|
| 35mm full-frame	| 43.1–43.3	| 35.8–36	| 23.9–24	| 856–864| 	1

It is important to note that the crop factor is related to the ratio of the camera sensor’s size to a 35 mm film frame.

Crop Factor = Diagonal_35mm / Diagonal_sensor


## How to choose the right CMOS sensor size for an embedded vision application
Each application has different sensor size requirements to produce images. Let us discuss the factors to be considered while choosing a sensor of a particular size.

- Resolution
- High frame rate and global shutter
- Sensitivity
- Lens mount selection
- Image circle diameter
- Low light performance

### Resolution
Resolution is the ability of imaging systems to reproduce the exact object detail. Many embedded vision applications like autonomous mobile robots (AMR) and autonomous vehicles demand cameras to achieve precise 3D depth measurement. This would be achieved with the high-resolution feature of that camera. Selecting sensors with large pixel sizes is likely to have higher resolution. Also, the resolution of the lens must match the pixel size of the sensor to achieve high-quality images. The quite popular camera resolution of 1600 x 1200 pixels often uses a larger sensor with a size of 1/1.8″, and now high-end 4K resolution uses a 1/1.2″ image sensor format.

### High Frame Rate and Global Shutter
Embedded vision applications like automated license plate recognition, gesture recognition, robotic vision, drones, and AMR require high frame rate and global shutter features – depending on the nature of the end application. AR0234 from Onsemi is one of the most popular sensors used in such applications. It is a 1/2.6″ (Diagonal 6.8 mm) optical format CMOS sensor with a 3.0 μm x 3.0 μm pixel size. It is a global shutter sensor that is used for accurate and fast capture of moving scenes at 120 frames per second at full resolution. See3CAM24_CUG from e-con Systems is a color global shutter camera based on the ARO234 sensor.

Also, some of the other available sensor sizes are 1/2.9″ (for Omnivision’s OV2311 CMOS image sensor with 3.0 μm x 3.0 μm pixel size) and 1/3″ (Onsemi’s AR0134 CMOS digital image sensor with an active pixel array of 1280H x. 960V).

### Sensitivity
Large sensors tend to have large pixel sizes, and this indicates higher sensitivity. To achieve high sensitivity and compact design, an industrial camera usually uses a 1/2.8″ CMOS image sensor. This enables a high level of image recognition and detection performance for improved safety for smart city, surveillance, and traffic monitoring systems.

### Lens Mount Selection
Mount is used for attaching a lens to a camera body. The selection of mount depends on the sensor size. For instance, the C mount, which is the type of lens mount for machine vision cameras, is appropriate for a 1.5″ sensor. S mount lens, which is commonly used in industrial applications, is appropriate for a sensor size of 1/2″, 1/3″ or smaller.

### Image Circle Diameter
Industrial cameras might have issues like lens vignetting/lens shading, which is a gradual reduction of an image’s brightness or saturation from the image center to the four corners/ edges. This happens when the image format (or circle) of the lens is too small for the size of the sensor. So, to mitigate this, the image circle diameter must fit or be larger than the sensor size.

### Low-light Performance
As discussed before, a large sensor contains larger photosites that are more receptive to light, thereby enhancing the camera’s ability to capture low-light images in comparison to a small sensor. Two of the popular sensor sizes targeted for low light performance are 1/1.2″ ( such as the Sony® IMX485 based 4K-resolution CMOS image sensor) and 35mm full-frame.


Sources:
- https://www.e-consystems.com/blog/camera/technology/what-is-cmos-sensor-size-in-embedded-cameras-how-to-pick-the-right-sensor-size/#:~:text=The%20size%20of%20the%20CMOS,sensor%20size%20or%20optical%20format.
- https://www.e-consystems.com/blog/camera/technology/cmos-sensors-vs-ccd-sensors-why-cmos-sensors-are-ruling-the-world-of-embedded-vision/
